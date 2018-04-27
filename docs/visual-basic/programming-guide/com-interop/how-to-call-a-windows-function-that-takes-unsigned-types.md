---
title: 'Procedura: chiamare una funzione Windows che accetta tipi senza segno (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Windows functions [Visual Basic], calling
- unsigned data types [Visual Basic]
- UShort data type [Visual Basic], using
- functions [Visual Basic], calling Windows functions
- ULong data type [Visual Basic], using
- UInteger data type [Visual Basic], using
- data types [Visual Basic], using
- unsigned types [Visual Basic]
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types [Visual Basic], using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dd0738300ec846041e78f19836f29e7adff1c821
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>Procedura: chiamare una funzione Windows che accetta tipi senza segno (Visual Basic)
Se si utilizza una classe, modulo o struttura che dispone di membri di tipi integer senza segno, è possibile accedere a questi membri con Visual Basic.  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>Per chiamare una funzione Windows che accetta un tipo senza segno  
  
1.  Utilizzare un [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md) indicare a Visual Basic la libreria che contiene la funzione, quali il nome è in tale raccolta, qual è la sequenza di chiamata e come convertire le stringhe, la chiamata.  
  
2.  Nel `Declare` istruzione, utilizzare `UInteger`, `ULong`, `UShort`, o `Byte` come appropriato per ogni parametro con un tipo senza segno.  
  
3.  Consultare la documentazione per la funzione di Windows che si sta chiamando per trovare i nomi e i valori delle costanti utilizzate. Molte di queste vengono definite nel file winuser. H.  
  
4.  Dichiarare le costanti necessarie nel codice. Molte costanti Windows sono valori senza segno a 32 bit e devono essere dichiarate `As``UInteger`.  
  
5.  Chiamare la funzione nel modo normale. Nell'esempio seguente viene chiamata la funzione Windows `MessageBox`, che accetta un argomento di intero senza segno.  
  
    ```  
    Public Class windowsMessage  
        Private Declare Auto Function mb Lib "user32.dll" Alias "MessageBox" (  
            ByVal hWnd As Integer,   
            ByVal lpText As String,   
            ByVal lpCaption As String,   
            ByVal uType As UInteger) As Integer  
        Private Const MB_OK As UInteger = 0  
        Private Const MB_ICONEXCLAMATION As UInteger = &H30  
        Private Const IDOK As UInteger = 1  
        Private Const IDCLOSE As UInteger = 8  
        Private Const c As UInteger = MB_OK Or MB_ICONEXCLAMATION  
        Public Function messageThroughWindows() As String  
            Dim r As Integer = mb(0, "Click OK if you see this!",   
                "Windows API call", c)  
            Dim s As String = "Windows API MessageBox returned " &  
                 CStr(r)& vbCrLf & "(IDOK = " & CStr(IDOK) &  
                 ", IDCLOSE = " & CStr(IDCLOSE) & ")"  
            Return s  
        End Function  
    End Class  
    ```  
  
     È possibile testare la funzione `messageThroughWindows` con il codice seguente.  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  Il `UInteger`, `ULong`, `UShort`, e `SByte` tipi di dati non sono in parte il [indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), pertanto il codice conforme a CLS non è possibile utilizzare un componente che li utilizza.  
  
    > [!IMPORTANT]
    >  Effettua una chiamata a codice non gestito, ad esempio l'interfaccia di programmazione dell'applicazione di Windows (API), espone il codice a potenziali rischi di sicurezza.  
  
    > [!IMPORTANT]
    >  Chiama l'API di Windows è necessaria l'autorizzazione di codice non gestito, che può influire sulla relativa esecuzione in situazioni di attendibilità parziale. Per ulteriori informazioni, vedere <xref:System.Security.Permissions.SecurityPermission> e [le autorizzazioni di accesso di codice](http://msdn.microsoft.com/library/e5ae402f-6dda-4732-bbe8-77296630f675).  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Tipo di dati Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Tipo di dati UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Procedura dettagliata: Chiamata delle API di Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
