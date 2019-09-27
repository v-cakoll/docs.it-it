---
title: 'Procedura: Scrivere un metodo di estensione (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 31ccb18e0e6d1569764ec2a67201d7f758129425
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332763"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a>Procedura: Scrivere un metodo di estensione (Visual Basic)

I metodi di estensione consentono di aggiungere metodi a una classe esistente. Il metodo di estensione può essere chiamato come se fosse un'istanza di tale classe.

### <a name="to-define-an-extension-method"></a>Per definire un metodo di estensione

1. Aprire un'applicazione Visual Basic nuova o esistente in Visual Studio.

2. Nella parte superiore del file in cui si desidera definire un metodo di estensione, includere l'istruzione import seguente:

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. All'interno di un modulo nell'applicazione nuova o esistente, iniziare la definizione del metodo con l'attributo di estensione:

    ```vb
    <Extension()>
    ```

4. Dichiarare il metodo nel modo consueto, ad eccezione del fatto che il tipo del primo parametro deve essere il tipo di dati che si desidera estendere.

    ```vb
    <Extension()>
    Public Sub SubName(para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a>Esempio

 Nell'esempio seguente viene dichiarato un metodo di estensione nel modulo `StringExtensions`. Un secondo modulo, `Module1`, importa `StringExtensions` e chiama il metodo. Il metodo di estensione deve essere nell'ambito quando viene chiamato. Il metodo di estensione `PrintAndPunctuate` estende la classe <xref:System.String> con un metodo che Visualizza l'istanza di stringa seguita da una stringa di simboli di punteggiatura inviati come parametro.
  
```vb
' Declarations will typically be in a separate module.
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
        Console.WriteLine(aString & punc)
    End Sub

End Module
```

```vb
' Import the module that holds the extension method you want to use,
' and call it.

Imports ConsoleApplication2.StringExtensions

Module Module1
  
    Sub Main()
        Dim example = "Hello"
        example.PrintAndPunctuate("?")
        example.PrintAndPunctuate("!!!!")
    End Sub
    
End Module
```
  
 Si noti che il metodo viene definito con due parametri e viene chiamato con una sola. Il primo parametro, `aString`, nella definizione del metodo è associato a `example`, l'istanza di `String` che chiama il metodo. L'output dell'esempio è il seguente:
  
 ```console
 Hello?
 Hello!!!!
 ```
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [Metodi di estensione](extension-methods.md)
- [Istruzione Module](../../../language-reference/statements/module-statement.md)
- [Parametri e argomenti delle routine](procedure-parameters-and-arguments.md)
- [Ambito in Visual Basic](../declared-elements/scope.md)
