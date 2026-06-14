
RU:
Список ошибок и их методы решения:

- Failed to initialize service ( или же Failed to initialize driver ) => необходимо удалить Faceit, VGK ( если есть ), выключить Microsoft Defender через Defender control ( https://www.softportal.com/software-43861-defender-control.html )

Синие экраны смерти:

- MEMORY_MANAGMENT => сделать все вышеперечисленные шаги, выключить защиту DMA ядра, выключить KPTI ( A.K.A Spectre Mitigations ), выключить HVCI (VBS). Ввести следующие команды по-отдельности в командную строку от имени администратора и перезагрузить компьютер:

reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Memory Management" /v FeatureSettingsOverride /t REG_DWORD /d 3 /f
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Memory Management" /v FeatureSettingsOverrideMask /t REG_DWORD /d 3 /f

bcdedit /set hypervisorlaunchtype off

reg add HKLM\SYSTEM\CurrentControlSet\CI\Config /v "VulnerableDriverBlocklistEnable" /t REG_DWORD /d 0 /f

ENG:
List of errors and their solutions:

Failed to initialize service (or Failed to initialize driver) => you need to uninstall Faceit, VGK (if present), disable Microsoft Defender using Defender Control (https://www.softportal.com/software-43861-defender-control.html)

Blue screens of death:

MEMORY_MANAGEMENT => perform all the steps listed above, disable DMA kernel protection, disable KPTI (A.K.A. Spectre Mitigations), disable HVCI (VBS). Enter the following commands one by one in Command Prompt as administrator and restart your computer:

reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Memory Management" /v FeatureSettingsOverride /t REG_WORD /d 3 /f
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Memory Management" /v FeatureSettingsOverrideMask /t REG_WORD /d 3 /f

bcdedit /set hypervisorlaunchtype off

reg add HKLM\SYSTEM\CurrentControlSet\CI\Config /v "VulnerableDriverBlocklistEnable" /t REG_DWORD /d 0 /f
