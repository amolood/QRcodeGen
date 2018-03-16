# QRcodeGen
To generate qrcode using android with save as image class


# how to use CodeGenerator ?
in your activity 

```java
  generateCode(YOUR VALUE HERE);
```

# how to save with share our without ? 

First parameter is Boolean that do you want to share or not ? ture for save with share.
Second parameter is input value. Type (String)
Thirtd paramter is output. Type (Bitmap)
```java
saveAndShare(false, inputStr, output);
```

# SaveImage funcation ?

```java
private void saveAndShare(final boolean shouldShare, String name, Bitmap bitmap) {
        if(shouldShare) {
            AppUtils.showToast(mContext, getString(R.string.preparing));
        } else {
            AppUtils.showToast(mContext, getString(R.string.saving));
        }
        SaveImage saveImage = new SaveImage(name, bitmap);
        saveImage.setSaveListener(new SaveImage.SaveListener() {
            @Override
            public void onSaved(String savedTo) {
                if (shouldShare) {
                    AppUtils.share(mActivity, savedTo);
                } else {
                    AppUtils.showToast(mContext, getString(R.string.saved_to) +"'"+ Constants.SAVE_TO +"' "+getString(R.string.directory_in));
                }
            }
        });
        saveImage.execute();
    }
```
