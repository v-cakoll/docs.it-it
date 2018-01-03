---
title: Routine Main in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6de98ad4e470cd0becaf25f5a9a00c8095e44b15
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="main-procedure-in-visual-basic"></a>Routine Main in Visual Basic
Ogni applicazione di Visual Basic deve contenere una routine denominata `Main`. Questa procedura viene utilizzata come punto di partenza e controllo generale per l'applicazione. Le chiamate di .NET Framework la `Main` procedura quando è stata caricata l'applicazione ed è pronta per passare il controllo a esso. A meno che non si sta creando un'applicazione Windows Forms, è necessario scrivere il `Main` procedure per le applicazioni eseguite nel proprio.  
  
 `Main`contiene il codice che viene eseguito per primo. In `Main`, è possibile determinare il form da caricare per primo all'avvio del programma, scoprire se una copia dell'applicazione è già in esecuzione nel sistema, stabilire un set di variabili per l'applicazione o aprire un database che richiede l'applicazione.  
  
## <a name="requirements-for-the-main-procedure"></a>Requisiti per la procedura principale  
 Un file che viene eseguito nel proprio (in genere con estensione .exe) deve contenere un `Main` stored procedure. Una libreria (ad esempio con estensione dll) non viene eseguito nel propria e non richiede un `Main` stored procedure. Come indicato di seguito sono riportati i requisiti per i diversi tipi di progetti che è possibile creare:  
  
-   Applicazioni console vengono eseguite proprio, quindi è necessario specificare almeno uno `Main` stored procedure. .  
  
-   Esecuzione applicazioni di Windows Form. Tuttavia, il compilatore Visual Basic genera automaticamente un `Main` procedura ad un'applicazione e, non è necessario scrivere uno.  
  
-   Librerie di classi non richiedono un `Main` stored procedure. Sono incluse le librerie di controlli di Windows e librerie di controlli Web. Applicazioni Web vengono distribuite come librerie di classi.  
  
## <a name="declaring-the-main-procedure"></a>Dichiarazione della routine Main  
 Esistono quattro modi per dichiarare il `Main` stored procedure. O non può accettare argomenti e può o non restituire un valore.  
  
> [!NOTE]
>  Se si dichiara `Main` in una classe, è necessario utilizzare il `Shared` (parola chiave). In un modulo, `Main` non dovrà essere `Shared`.  
  
-   Il modo più semplice consiste nel dichiarare un `Sub` routine che non accetta argomenti e restituiscono un valore.  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   `Main`può inoltre restituire un `Integer` valore, il sistema operativo utilizza il codice di uscita per il programma. Altri programmi è possano testare questo codice esaminando il valore di ERRORLEVEL di Windows. Per restituire un codice di uscita, è necessario dichiarare `Main` come un `Function` procedure anziché un `Sub` stored procedure.  
  
    ```  
    Module mainModule  
        Function Main() As Integer  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' Insert call to appropriate starting place in your code.  
            ' On return, assign appropriate value to returnValue.  
            ' 0 usually means successful completion.  
            MsgBox("The application is terminating with error level " &  
                 CStr(returnValue) & ".")  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
-   `Main`può anche richiedere un `String` matrice come argomento. Ogni stringa della matrice contiene uno degli argomenti della riga di comando utilizzati per richiamare il programma. È possibile eseguire azioni diverse a seconda di valori.  
  
    ```  
    Module mainModule  
        Function Main(ByVal cmdArgs() As String) As Integer  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' See if there are any arguments.  
            If cmdArgs.Length > 0 Then  
                For argNum As Integer = 0 To UBound(cmdArgs, 1)  
                    ' Insert code to examine cmdArgs(argNum) and take  
                    ' appropriate action based on its value.  
                Next argNum  
            End If  
            ' Insert call to appropriate starting place in your code.  
            ' On return, assign appropriate value to returnValue.  
            ' 0 usually means successful completion.  
            MsgBox("The application is terminating with error level " &  
                 CStr(returnValue) & ".")  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
-   È possibile dichiarare `Main` per esaminare gli argomenti della riga di comando, ma non restituisce un codice di uscita, come indicato di seguito.  
  
    ```  
    Module mainModule  
        Sub Main(ByVal cmdArgs() As String)  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' See if there are any arguments.  
            If cmdArgs.Length > 0 Then  
                For argNum As Integer = 0 To UBound(cmdArgs, 1)  
                    ' Insert code to examine cmdArgs(argNum) and take  
                    ' appropriate action based on its value.  
                Next argNum  
            End If  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
 <xref:System.Array.Length%2A>  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [Struttura di un programma Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [/main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Tipo di dati Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Tipo di dati String](../../../visual-basic/language-reference/data-types/string-data-type.md)
