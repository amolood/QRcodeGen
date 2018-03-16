# QRcodeGen
To generate qrcode using android with save as image class


# how to use CodeGenerator ?
in your activity 
  generateCode(YOUR VALUE HERE);
  
  
# how to use SaveImage ?

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
