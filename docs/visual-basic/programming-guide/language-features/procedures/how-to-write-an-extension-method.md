---
title: 'Procedura: Scrivere un metodo di estensione (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 019104956b21e527c0498c286d85da27abdc5695
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576071"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a>Procedura: Scrivere un metodo di estensione (Visual Basic)
I metodi di estensione consentono di aggiungere metodi a una classe esistente. Il metodo di estensione può essere chiamato come se fosse un'istanza di tale classe.  
  
### <a name="to-define-an-extension-method"></a>Per definire un metodo di estensione  
  
1.  Aprire un'applicazione nuova o esistente di Visual Basic in Visual Studio.  
  
2.  Nella parte superiore del file in cui si desidera definire un metodo di estensione, includere l'istruzione import seguente:  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  All'interno di un modulo nell'applicazione nuovo o esistente, inizia con la definizione del metodo con l'attributo di estensione:  
  
    ```  
    <Extension()>  
    ```  
  
4.  Dichiarare il metodo in modo normale, ad eccezione del fatto che il tipo del primo parametro deve essere il tipo di dati da estendere.  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a>Esempio  
 L'esempio seguente dichiara un metodo di estensione nel modulo `StringExtensions`. Un secondo modulo `Module1`, Importa `StringExtensions` e chiama il metodo. Il metodo di estensione deve essere nell'ambito quando viene chiamato. Metodo di estensione `PrintAndPunctuate` estende il <xref:System.String> classe con un metodo che visualizza l'istanza di stringa seguita da una stringa di segni di punteggiatura inviato come parametro in.  
  
```vb  
' Declarations will typically be in a separate module.  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
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
  
 Si noti che il metodo viene definito con due parametri e denominato con una sola. Il primo parametro, `aString`, nel metodo di definizione è associato a `example`, l'istanza di `String` che chiama il metodo. L'output dell'esempio è il seguente:  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [Metodi di estensione](./extension-methods.md)
- [Istruzione Module](../../../../visual-basic/language-reference/statements/module-statement.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
