# LimaCharlie D&R Lab: Volume Shadow Copy Deletion

In this section, we are testing LimaCharlie’s Detection & Response (D&R) capabilities. Specifically, we simulate a common ransomware behavior—deleting Volume Shadow Copies—and observe how default Sigma rules detect this activity. We also create a response rule that terminates the offending process, demonstrating automated defense in action.

---

# Detection Steps

```bash
# 1. Review Detection
# - Open LimaCharlie’s Detection tab
# - Locate the event triggered by `vssadmin delete shadows /all`
# - Expand detection to examine metadata and references
# - View the Timeline to see the raw event
```
[Timeline](./screenshots/limacharlie%20timeline%20telemetry.png)
```
# 2. Create a D&R Response Rule
# - Navigate to Respond section
# - Add new rule:
```
[D&R Rule](./screenshots/Create%20Detection%20Rule.png)
```
# - Save rule as `vss_deletion_kill_it`
# - Explanation:
#   - `action: report` sends a detection report to the Detections tab
#   - `action: task` kills the parent process running `vssadmin delete shadows /all`
```
 
```
# 3. Test the Rule
# - Return to your Sliver C2 session
vssadmin delete shadows /all
```
 
```
# - Expected behavior:
#   - Command succeeds
#   - D&R rule triggers and terminates parent process

# 4. Confirm Detection
# - Go back to the Detections screen
# - Verify that `vss_deletion_kill_it` rule fired
```
[Confirm Detection & Process Termination](./screenshots/Limacharlie%20detection.png)

