### protege
---
https://github.com/protegeproject/protege

https://protege.stanford.edu/

```java
// protege-editor-core/src/test/java/org/protege/editor/core/platform/apple/MacUUtil_TestCase.java

public class MacUIUtil_TestCase {
  
  public static final WIndow PARENT = new JFrame();
  
  @Before
  public void setup() throws Exception {
  }
  
  @Test
  public void shouldAcceptNullExtensionArg() {
    try {
      showDialog(() -> MacUIUtil.saveFile(PARENT, "Title", null, "Initial name"));
    } catch (Exception e) {
      faile(e.getMessage());
    }
  }
  
  @Test
  public void shouldAcceptNullInitialName() {
    try {
      showDialog(() -> MacUIUtil.saveFile(PARENT, "Title", Collections.emptySet(), null));
    } catch(Exception e) {
      fail(e.getMessage());
    }
  }
  
  private void showDialong(Runner r) {
    SwingUtilities.invokeLater(() -> {
      try {
        r.run();
      } catch (Exception e) {
        fail(e.getMessage());
      }
    });
    waitForFileDialog();
  }
  
  private void waitForFileDialong() {
    try {
      for(int i = 0; i < 10; i++) {
        if (windows != null && windows.length > 0) {
          for(Window w : windows) {
            if(w instanceof FileDialog) {
              Thread.sleep(500);
              return;
            }
          }
        }
        Thread.sleep(500);
      }
      fail("Dialog not shown");
    } catch (InterruptedException e) {
      fail(e.getMessage());
    }
  }
}
```

```
```

```
```


