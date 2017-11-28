---
title: 'Procedura: scrivere un metodo di estensione (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65cdabf59886e7457a327ee9cde968a6a73f2280
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-an-extension-method-visual-basic"></a>Procedura: scrivere un metodo di estensione (Visual Basic)
Metodi di estensione consentono di aggiungere metodi alla classe esistente. Il metodo di estensione può essere chiamato come se fosse un'istanza di tale classe.  
  
### <a name="to-define-an-extension-method"></a>Per definire un metodo di estensione  
  
1.  Aprire un'applicazione nuova o esistente di Visual Basic in Visual Studio.  
  
2.  Nella parte superiore del file in cui si desidera definire un metodo di estensione, includere l'istruzione di importazione seguente:  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  All'interno di un modulo nuovo o esistente nell'applicazione in uso, iniziare la definizione di metodo con l'attributo di estensione:  
  
    ```  
    <Extension()>  
    ```  
  
4.  Dichiarare il metodo in modo normale, ad eccezione del fatto che il tipo del primo parametro deve essere il tipo di dati che si desidera estendere.  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene dichiarato un metodo di estensione nel modulo `StringExtensions`. Un secondo modulo `Module1`, Importa `StringExtensions` e chiama il metodo. Il metodo di estensione deve essere nell'ambito quando viene chiamato. Metodo di estensione `PrintAndPunctuate` estende la <xref:System.String> classe con un metodo che visualizza l'istanza di stringa seguiti da una stringa di segni di punteggiatura inviati come parametro.  
  
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
  
 Si noti che il metodo viene definito con due parametri e chiamato con una sola. Il primo parametro, `aString`, nel metodo di definizione è associato a `example`, l'istanza di `String` che chiama il metodo. L'output dell'esempio è la seguente:  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>  
 [Metodi di estensione](./extension-methods.md)  
 [Istruzione Module](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Ambito in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
