exec-once = $UserScripts/RainbowBorders.sh
binde = , xf86MonBrightnessDown, exec, $scriptsDir/Brightness.sh --dec # decrease monitor brightness
binde = , xf86MonBrightnessUp, exec, $scriptsDir/Brightness.sh --inc # increase monitor brightness
bind = $mainMod ALT, V, exec, $scriptsDir/ClipManager.sh # Clipboard Manager
bind = $mainMod ALT, mouse_down, exec, hyprctl keyword cursor:zoom_factor "$(hyprctl getoption cursor:zoom_factor | awk 'NR==1 {factor = $2; if (factor < 1) {factor = 1}; print factor * 2.0}')"
bind = $mainMod ALT, mouse_up, exec, hyprctl keyword cursor:zoom_factor "$(hyprctl getoption cursor:zoom_factor | awk 'NR==1 {factor = $2; if (factor < 1) {factor = 1}; print factor / 2.0}')" 
bind = $mainMod, P, exec, hyprctl --batch 'dispatch togglefloating ; dispatch pin'
bind = $mainMod SHIFT, Q, exec, $scriptsDir/KillActiveProcess.sh # Kill active process
bindel = , xf86audioraisevolume, exec, $scriptsDir/Volume.sh --inc # volume up
bindel = , xf86audiolowervolume, exec, $scriptsDir/Volume.sh --dec # volume down
bindl = , xf86AudioMicMute, exec, $scriptsDir/Volume.sh --toggle-mic # mic mute
bindl = , xf86audiomute, exec, $scriptsDir/Volume.sh --toggle # mute
bindl = , xf86Rfkill, exec, $scriptsDir/AirplaneMode.sh # Airplane mode
# Screenshot keybindings NOTE: You may need to press Fn key as well
bind = $mainMod, Print, exec, $scriptsDir/ScreenShot.sh --now  # screenshot
bind = $mainMod SHIFT, Print, exec, $scriptsDir/ScreenShot.sh --area # screenshot (area)
bind = $mainMod CTRL, Print, exec, $scriptsDir/ScreenShot.sh --in5 # screenshot  (5 secs delay)
bind = $mainMod CTRL SHIFT, Print, exec, $scriptsDir/ScreenShot.sh --in10 # screenshot (10 secs delay)
bind = ALT, Print, exec, $scriptsDir/ScreenShot.sh --active # screenshot (active window only)
# Resize windows
binde = $mainMod SHIFT, left, resizeactive,-50 0
binde = $mainMod SHIFT, right, resizeactive,50 0
binde = $mainMod SHIFT, up, resizeactive,0 -50
binde = $mainMod SHIFT, down, resizeactive,0 50

# Move windows
bind = $mainMod CTRL, left, movewindow, l
bind = $mainMod CTRL, right, movewindow, r
bind = $mainMod CTRL, up, movewindow, u
bind = $mainMod CTRL, down, movewindow, d
# Swap windows
bind = $mainMod ALT, left, swapwindow, l
bind = $mainMod ALT, right, swapwindow, r
bind = $mainMod ALT, up, swapwindow, u
bind = $mainMod ALT, down, swapwindow, d
# Workspaces related
bind = $mainMod, tab, workspace, m+1
bind = $mainMod SHIFT, tab, workspace, m-1
# Move active window to a workspace silently mainMod + CTRL [0-9]
bind = $mainMod CTRL, code:10, movetoworkspacesilent, 1 # NOTE: code:10 = key 1
bind = $mainMod CTRL, code:11, movetoworkspacesilent, 2 # NOTE: code:11 = key 2
bind = $mainMod CTRL, code:12, movetoworkspacesilent, 3 # NOTE: code:12 = key 3
bind = $mainMod CTRL, code:13, movetoworkspacesilent, 4 # NOTE: code:13 = key 4
bind = $mainMod CTRL, code:14, movetoworkspacesilent, 5 # NOTE: code:14 = key 5
bind = $mainMod CTRL, code:15, movetoworkspacesilent, 6 # NOTE: code:15 = key 6
bind = $mainMod CTRL, code:16, movetoworkspacesilent, 7 # NOTE: code:16 = key 7
bind = $mainMod CTRL, code:17, movetoworkspacesilent, 8 # NOTE: code:17 = key 8
bind = $mainMod CTRL, code:18, movetoworkspacesilent, 9 # NOTE: code:18 = key 9
bind = $mainMod CTRL, code:19, movetoworkspacesilent, 10 # NOTE: code:19 = key 0
# Scroll through existing workspaces with mainMod + scroll
bind = $mainMod, mouse_down, workspace, e+1
bind = $mainMod, mouse_up, workspace, e-1
# Move/resize windows with mainMod + LMB/RMB and dragging
bindm = $mainMod, mouse:272, movewindow # NOTE: mouse:272 = left click
bindm = $mainMod, mouse:273, resizewindow # NOTE: mouse:273 = right click

$scriptsDir = $HOME/.config/hypr/scripts

exec-once = swaync
