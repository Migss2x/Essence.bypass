Start-Process powershell -ArgumentList '-NoExit', '-Command', @"
Add-Type @"
using System;
using System.Runtime.InteropServices;
public class Win {
  [DllImport("user32.dll")] public static extern bool MoveWindow(IntPtr h, int x, int y, int w, int h, bool r);
  [DllImport("user32.dll")] public static extern IntPtr GetForegroundWindow();
}
"@
$h = [Win]::GetForegroundWindow()
Start-Sleep -Milliseconds 300
[Win]::MoveWindow($h, 0, 0, 300, 400, $true)
cmd /k "echo testing"
"@
