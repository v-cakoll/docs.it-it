---
title: 'Procedura: Chiamare un metodo di estensione (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: 5cb0684637a716dfec947740ba345c62eaabddd7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59313801"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a>Procedura: Chiamare un metodo di estensione (Visual Basic)
I metodi di estensione consentono di aggiungere metodi a una classe esistente. Dopo che un metodo di estensione è dichiarato e inserito nell'ambito, è possibile chiamarlo come metodo di istanza del tipo che estende. Per altre informazioni su come scrivere un metodo di estensione, vedere [come: Scrivere un metodo di estensione](./how-to-write-an-extension-method.md).  
  
 Le istruzioni seguenti fanno riferimento al metodo di estensione `PrintAndPunctuate`, che consentirà di visualizzare l'istanza di stringa che lo richiama, seguita dal valore viene inviato per il secondo parametro, `punc`.  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 Il metodo deve essere nell'ambito quando viene chiamato.  
  
### <a name="to-call-an-extension-method"></a>Per chiamare un metodo di estensione  
  
1. Dichiarare una variabile con il tipo di dati del primo parametro del metodo di estensione. Per la `PrintAndPunctuate`, è necessario un <xref:System.String> variabile:  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2. Variabile richiamerà il metodo di estensione che il relativo valore è associato al primo parametro, `aString`. Verrà visualizzata la seguente istruzione chiama `Ready?`.  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     Si noti che la chiamata a questo metodo di estensione, ad esempio una chiamata a uno qualsiasi del <xref:System.String> metodi che richiedono un parametro di istanza:  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3. Dichiarare un'altra variabile string e chiamare nuovamente il metodo per verificare che funziona con qualsiasi stringa.  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     In questo caso il risultato è: `or not!!!`.  
  
## <a name="example"></a>Esempio  
 Il codice seguente è un esempio completo della creazione e utilizzo di un metodo di estensione semplice.  
  
```vb  
Imports System.Runtime.CompilerServices  
Imports ConsoleApplication1.StringExtensions  
  
Module Module1  
  
    Sub Main()  
  
        Dim example = "Hello"  
        example.PrintAndPunctuate(".")  
        example.PrintAndPunctuate("!!!!")  
  
        Dim example2 = "Goodbye"  
        example2.PrintAndPunctuate("?")  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
End Module  
  
' Output:  
' Hello.  
' Hello!!!!  
' Goodbye?  
```  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Scrivere un metodo di estensione](./how-to-write-an-extension-method.md)
- [Metodi di estensione](./extension-methods.md)
- [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
