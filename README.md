# PagerSlidingTabStrip
你还在为监听键盘的打开还是关闭而烦恼吗?怎么获取键盘高度?第三方那么多!
out了!!,不一定out...
这里提供一种方法
#原理分析与实现
通过计算布局中的android.R.id.content的可见高度来计算.
# 效果图
<img src="/screenshots/1.png"/>
<img src="/screenshots/2.png"/>
# 使用方法 

```java
KeyBordStateUtil keyBordStateUtil=new KeyBordStateUtil(this);
keyBordStateUtil.addOnKeyBordStateListener(mOnKeyBordStateListener);
  
private KeyBordStateUtil.onKeyBordStateListener mOnKeyBordStateListener = new KeyBordStateUtil.onKeyBordStateListener() {

    @Override
    public void onSoftKeyBoardShow(int keyboardHeight) {
        textView.setText("键盘打开了-高度为:" + keyboardHeight);
    }

    @Override
    public void onSoftKeyBoardHide() {
        textView.setText("键盘关闭了");
    }
};

//释放,防止内存泄漏哦!
 @Override
    protected void onDestroy() {
        super.onDestroy();
        keyBordStateUtil.removeOnKeyBordStateListener();
    }
```
  