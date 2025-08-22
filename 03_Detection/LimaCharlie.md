# LimaCharlie D&R Lab: VSS Deletion Test

```bash
# 1. Review Detection
# - Open LimaCharlie’s Detection tab
# - Locate the event triggered by `vssadmin delete shadows /all`
# - Expand detection to examine all metadata and references
# - View the Timeline to see the raw event

# 2. Create a D&R Response Rule
# Respond section -> add new rule

# Add action to terminate parent process of offending command
action: task
command: deny_tree
target: <<routing/parent>>

# Save rule as: vss_deletion_kill_it
# Explanation:
# - `action: report` -> sends detection report to Detections tab
# - `action: task` -> kills parent process running `vssadmin delete shadows /all`
#   Simulates stopping ransomware or lateral movement tool

# 3. Test the Rule
# - Return to your Sliver C2 session
vssadmin delete shadows /all

# Expected behavior:
# - Command succeeds
# - D&R rule triggers and terminates parent process
# - System shell will hang when running:
whoami
#   (No output indicates parent process terminated)

# 4. Confirm Detection
# - Go to Detections screen
# - Verify that `vss_deletion_kill_it` rule fired

