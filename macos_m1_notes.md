# Things that are working
1. Terminal using iterm2 (external installation) support customization and multitabs
2. VScode (external installation)
3. Brave (external installation), Brave has different key bindings (Command instead of Control) and changing is possible just using extensions
4. Apple Main client works great with Gmail/O365 or custom mail server
5. Signal messanger only works using Rosetta emulator (mac offers to install it automatically)
6. Wireguard,OpenVPN,Forticlient works after installing external application. No native support
7. Ansible and Terraform can be installed via brew (First need to install homebrew)
8. External monitors and scalling
9. Brave/Chrome remap Command-T/W to Control-T/W. Go to keyboard shortcuts,App shortcuts and make special "New Tab" and "Close Tab" shortcut. You must keep exact names
10. Same as number 9 you need to add custom for All application "Copy" "Paste" "Undo" to ctrl+c/v/z
11. To external keyboard to have same as laptop keyboard you need to switch Command<->Option
12. Photoshop and Lightroom are natively for M1 and works very fast
13. Other Adobe SW works using Rosetta translator, we did tests with Ilustrator/Premiere and performance is same as they have it now
14. LibreOffice 7.1 works well. No performance difference noticed by Brittany
15. Docker works natively for ARM processor
16. I tried Google Ads, many tabs, keep it running and it does not effect performance or memory consumption


# Things annoy me
1. Logitec mouse I could connect via Blootooth. Macos has Mouse connector but only for Apple mouse. This BT mouse feels a bit laggy sometimes (I didnt use dongle as no USB port in MacBook Air)
2. I got a feeling that in Apple store I never found anything I need
3. Randomly sometimes windows jumps from one virtual desktop to another and I have no idea why :) - this can be solved by settings
4. Lot of customization for keys and shortcut needed for linux/windows user
5. Animations you cant switch it off completely 

# Not working and annoying things
1. Check for updates was never finishing first one week of usage. Out of nothing was fine
2. When I enabled firewall whole PC frozed, I needed to restart. Random behaviour.
3. Layout switching is buggy, sometimes works sometimes not
4. Sometimes key remaping after reboot got to previous state

# Advantages over Tuxedo with linux
1. Touchpad and Mouse gestures are fantastic
2. Scaling across various displays works like charm
3. Construction of the laptop is much better.
4. Touch ID
5. Laptop is cold even during usage
6. Baterry last much longer
7. CHarging over USB-C + display, so only one cable needed

# Advantages of Tuxedo
1. Having much more inputs, M1 Air has only 2 USB-C
2. Customization of Linux, various options how to addapt desktop to your needs
3. Upgrades are much faster. In M1 it takes very long time, linux upgrades are very fast.

# Useful Tricks
## Keyboard hacks
Put this to ~/Library/KeyBindings/DefaultKeyBinding.dict
```
{
  "\UF729"  = moveToBeginningOfParagraph:; // home
  "\UF72B"  = moveToEndOfParagraph:; // end
  "$\UF729" = moveToBeginningOfParagraphAndModifySelection:; // shift-home
  "$\UF72B" = moveToEndOfParagraphAndModifySelection:; // shift-end
  "^\UF729" = moveToBeginningOfDocument:; // ctrl-home
  "^\UF72B" = moveToEndOfDocument:; // ctrl-end
  "^$\UF729" = moveToBeginningOfDocumentAndModifySelection:; // ctrl-shift-home
  "^$\UF72B" = moveToEndOfDocumentAndModifySelection:; // ctrl-shift-end
  "^v" = noop:; // cancel ctrl+v to do pg-down
}
```

## Terraform tricks
### FIX not able to connect via SSH to ec2 when created 
This one is because we need to specify in `~/.ssh/config` the parameter: `AddKeysToAgent yes`    as for example:

```
Host eatcobra.medojed.info
  Port 42335
  User admin
  StrictHostKeyChecking no
  IdentityFile ~/.ssh/wiki_rsa
  AddKeysToAgent yes

Host 10.*
  ProxyCommand ssh -W %h:%p eatcobra.medojed.info
  StrictHostKeyChecking no
  IdentityFile ~/.ssh/wiki_rsa
  AddKeysToAgent yes
 

```
