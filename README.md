
# RegSettings for VB.NET
This code will save program settings on your own key under `"CurrentUser\Software\[CompanyName]\[ApplicationName]"`
The code works in a similar way the SaveSetting, GetSetting and DeleteSetting but allowing to be hosted under your "**CompanyName"** and "**ApplicationName"** key on the registry for better management. 

### Files

Only Module [RegSettings.vb](https://github.com/limbo666/RegSettings_for_VB.NET/blob/main/Module/RegSettings.vb "RegSettings.vb") is needed. Add it to your project and call the functions as necessary.

### Calling the functions
Assuming that you want to save your form top value `Form1.top` and your form left value `Form1.left` you can use the following two lines:

    RegSaveSetting("Settings", "Top", Me.Top)
    RegSaveSetting("Settings", "Left", Me.Left)

To restore these values you can just get these values back by adding a default value in case that the registry key is missing.

    Me.Top = RegGetSetting("Settings", "Top", 200)
    Me.Left = RegGetSetting("Settings", "Left", 200)


### Functions available
`RegSaveSetting` Saves value to registry key specified
`RegGetSetting` Retrieves value if exists otherwise returns the default passed on function calling
`RegDeleteSetting` Deletes the value and the key
`RegDeleteAllSettings` Deletes all settings stored under Program Name 


### Important notes
Function `RegGetSetting` detects the data type to be returned by the default value provided during coding. It is important to pass the correct data type on "default value".
