# Uni Editor GUI Layout Wrapper

using static を使用して OnGUI の記述を少し楽にするエディタ拡張

## 使用例

### 通常

```cs
using UnityEditor;
using UnityEngine;

public class Example : EditorWindow
{
    [MenuItem( "Tools/Hoge" )]
    private static void Open()
    {
        GetWindow<Example>();
    }

    private void OnGUI()
    {
        EditorGUILayout.BeginHorizontal();

        if ( GUILayout.Button( "ピカチュウ" ) )
        {
        }

        if ( GUILayout.RepeatButton( "ライチュウ" ) )
        {
        }

        EditorGUILayout.EndHorizontal();

        EditorGUILayout.BeginHorizontal();
        EditorGUILayout.PrefixLabel( "ああああ" );
        EditorGUILayout.TextField( "いいいい" );
        EditorGUILayout.EndHorizontal();
    }
}
```

### Uni Editor GUI Layout Wrapper

```cs
using UnityEditor;
using static UniEditorGUILayoutWrapper.EditorGUILayoutWrapper;

public class Example : EditorWindow
{
    [MenuItem( "Tools/Hoge" )]
    private static void Open()
    {
        GetWindow<Example>();
    }

    private void OnGUI()
    {
        BeginHorizontal();

        if ( Button( "ピカチュウ" ) )
        {
        }

        if ( RepeatButton( "ライチュウ" ) )
        {
        }

        EndHorizontal();

        BeginHorizontal();
        PrefixLabel( "ああああ" );
        TextField( "いいいい" );
        EndHorizontal();
    }
}
```

## 関連記事

* http://baba-s.hatenablog.com/entry/2019/12/05/080000