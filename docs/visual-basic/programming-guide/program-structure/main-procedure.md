---
title: Procedura principale
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: cf6003206566dfe8f70a7f75cd4d7ec7565794a5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403174"
---
# <a name="main-procedure-in-visual-basic"></a>Routine Main in Visual Basic
Ogni applicazione Visual Basic deve contenere una procedura denominata `Main` . Questa procedura funge da punto di partenza e controllo generale per l'applicazione. Il .NET Framework chiama la `Main` procedura quando ha caricato l'applicazione ed è pronta per passare il controllo. A meno che non si stia creando una Windows Forms Application, è necessario scrivere la `Main` procedura per le applicazioni che vengono eseguite autonomamente.

 `Main`contiene il codice che viene eseguito per primo. In `Main` è possibile determinare il modulo da caricare per primo all'avvio del programma, verificare se una copia dell'applicazione è già in esecuzione nel sistema, stabilire un set di variabili per l'applicazione o aprire un database necessario per l'applicazione.

## <a name="requirements-for-the-main-procedure"></a>Requisiti per la procedura principale
 Un file che viene eseguito autonomamente, in genere con estensione exe, deve contenere una `Main` routine. Una libreria, ad esempio con estensione dll, non viene eseguita autonomamente e non richiede una `Main` procedura. I requisiti per i diversi tipi di progetti che è possibile creare sono i seguenti:

- Le applicazioni console vengono eseguite autonomamente ed è necessario fornire almeno una `Main` procedura.

- Windows Forms le applicazioni vengono eseguite autonomamente. Tuttavia, il compilatore Visual Basic genera automaticamente una `Main` procedura in tale applicazione e non è necessario scriverne una.

- Le librerie di classi non richiedono una `Main` procedura. Sono incluse le librerie di controlli Windows e le librerie di controlli Web. Le applicazioni Web vengono distribuite come librerie di classi.

## <a name="declaring-the-main-procedure"></a>Dichiarazione della routine Main
 Esistono quattro modi per dichiarare la `Main` procedura. Può assumere o meno argomenti e può restituire un valore.

> [!NOTE]
> Se si dichiara `Main` in una classe, è necessario usare la `Shared` parola chiave. In un modulo `Main` non è necessario che sia `Shared` .

- Il modo più semplice consiste nel dichiarare una `Sub` routine che non accetta argomenti o restituisce un valore.

    ```vb
    Module mainModule
        Sub Main()
            MsgBox("The Main procedure is starting the application.")
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```

- `Main`può inoltre restituire un `Integer` valore, che viene utilizzato dal sistema operativo come codice di uscita per il programma. Altri programmi possono testare questo codice esaminando il valore ERRORLEVEL di Windows. Per restituire un codice di uscita, è necessario dichiarare `Main` come `Function` routine anziché come `Sub` routine.

    ```vb
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

- `Main`può inoltre assumere una `String` matrice come argomento. Ogni stringa della matrice contiene uno degli argomenti della riga di comando usati per richiamare il programma. È possibile eseguire azioni diverse a seconda dei rispettivi valori.

    ```vb
    Module mainModule
        Function Main(ByVal cmdArgs() As String) As Integer
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
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

- È possibile dichiarare `Main` per esaminare gli argomenti della riga di comando, ma non per restituire un codice di uscita, come indicato di seguito.

    ```vb
    Module mainModule
        Sub Main(ByVal cmdArgs() As String)
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
            End If
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [Struttura di un programma Visual Basic](structure-of-a-visual-basic-program.md)
- [-main](../../reference/command-line-compiler/main.md)
- [Condivisa](../../language-reference/modifiers/shared.md)
- [Istruzione Sub](../../language-reference/statements/sub-statement.md)
- [Istruzione Function](../../language-reference/statements/function-statement.md)
- [Tipo di dati Integer](../../language-reference/data-types/integer-data-type.md)
- [Tipo di dati String](../../language-reference/data-types/string-data-type.md)
