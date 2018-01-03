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
# <a name="main-procedure-in-visual-basic"></a><span data-ttu-id="789cd-102">Routine Main in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="789cd-102">Main Procedure in Visual Basic</span></span>
<span data-ttu-id="789cd-103">Ogni applicazione di Visual Basic deve contenere una routine denominata `Main`.</span><span class="sxs-lookup"><span data-stu-id="789cd-103">Every Visual Basic application must contain a procedure called `Main`.</span></span> <span data-ttu-id="789cd-104">Questa procedura viene utilizzata come punto di partenza e controllo generale per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="789cd-104">This procedure serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="789cd-105">Le chiamate di .NET Framework la `Main` procedura quando è stata caricata l'applicazione ed è pronta per passare il controllo a esso.</span><span class="sxs-lookup"><span data-stu-id="789cd-105">The .NET Framework calls your `Main` procedure when it has loaded your application and is ready to pass control to it.</span></span> <span data-ttu-id="789cd-106">A meno che non si sta creando un'applicazione Windows Forms, è necessario scrivere il `Main` procedure per le applicazioni eseguite nel proprio.</span><span class="sxs-lookup"><span data-stu-id="789cd-106">Unless you are creating a Windows Forms application, you must write the `Main` procedure for applications that run on their own.</span></span>  
  
 <span data-ttu-id="789cd-107">`Main`contiene il codice che viene eseguito per primo.</span><span class="sxs-lookup"><span data-stu-id="789cd-107">`Main` contains the code that runs first.</span></span> <span data-ttu-id="789cd-108">In `Main`, è possibile determinare il form da caricare per primo all'avvio del programma, scoprire se una copia dell'applicazione è già in esecuzione nel sistema, stabilire un set di variabili per l'applicazione o aprire un database che richiede l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="789cd-108">In `Main`, you can determine which form is to be loaded first when the program starts, find out if a copy of your application is already running on the system, establish a set of variables for your application, or open a database that the application requires.</span></span>  
  
## <a name="requirements-for-the-main-procedure"></a><span data-ttu-id="789cd-109">Requisiti per la procedura principale</span><span class="sxs-lookup"><span data-stu-id="789cd-109">Requirements for the Main Procedure</span></span>  
 <span data-ttu-id="789cd-110">Un file che viene eseguito nel proprio (in genere con estensione .exe) deve contenere un `Main` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="789cd-110">A file that runs on its own (usually with extension .exe) must contain a `Main` procedure.</span></span> <span data-ttu-id="789cd-111">Una libreria (ad esempio con estensione dll) non viene eseguito nel propria e non richiede un `Main` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="789cd-111">A library (for example with extension .dll) does not run on its own and does not require a `Main` procedure.</span></span> <span data-ttu-id="789cd-112">Come indicato di seguito sono riportati i requisiti per i diversi tipi di progetti che è possibile creare:</span><span class="sxs-lookup"><span data-stu-id="789cd-112">The requirements for the different types of projects you can create are as follows:</span></span>  
  
-   <span data-ttu-id="789cd-113">Applicazioni console vengono eseguite proprio, quindi è necessario specificare almeno uno `Main` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="789cd-113">Console applications run on their own, and you must supply at least one `Main` procedure.</span></span> <span data-ttu-id="789cd-114">.</span><span class="sxs-lookup"><span data-stu-id="789cd-114">.</span></span>  
  
-   <span data-ttu-id="789cd-115">Esecuzione applicazioni di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="789cd-115">Windows Forms applications run on their own.</span></span> <span data-ttu-id="789cd-116">Tuttavia, il compilatore Visual Basic genera automaticamente un `Main` procedura ad un'applicazione e, non è necessario scrivere uno.</span><span class="sxs-lookup"><span data-stu-id="789cd-116">However, the Visual Basic compiler automatically generates a `Main` procedure in such an application, and you do not need to write one.</span></span>  
  
-   <span data-ttu-id="789cd-117">Librerie di classi non richiedono un `Main` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="789cd-117">Class libraries do not require a `Main` procedure.</span></span> <span data-ttu-id="789cd-118">Sono incluse le librerie di controlli di Windows e librerie di controlli Web.</span><span class="sxs-lookup"><span data-stu-id="789cd-118">These include Windows Control Libraries and Web Control Libraries.</span></span> <span data-ttu-id="789cd-119">Applicazioni Web vengono distribuite come librerie di classi.</span><span class="sxs-lookup"><span data-stu-id="789cd-119">Web applications are deployed as class libraries.</span></span>  
  
## <a name="declaring-the-main-procedure"></a><span data-ttu-id="789cd-120">Dichiarazione della routine Main</span><span class="sxs-lookup"><span data-stu-id="789cd-120">Declaring the Main Procedure</span></span>  
 <span data-ttu-id="789cd-121">Esistono quattro modi per dichiarare il `Main` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="789cd-121">There are four ways to declare the `Main` procedure.</span></span> <span data-ttu-id="789cd-122">O non può accettare argomenti e può o non restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="789cd-122">It can take arguments or not, and it can return a value or not.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="789cd-123">Se si dichiara `Main` in una classe, è necessario utilizzare il `Shared` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="789cd-123">If you declare `Main` in a class, you must use the `Shared` keyword.</span></span> <span data-ttu-id="789cd-124">In un modulo, `Main` non dovrà essere `Shared`.</span><span class="sxs-lookup"><span data-stu-id="789cd-124">In a module, `Main` does not need to be `Shared`.</span></span>  
  
-   <span data-ttu-id="789cd-125">Il modo più semplice consiste nel dichiarare un `Sub` routine che non accetta argomenti e restituiscono un valore.</span><span class="sxs-lookup"><span data-stu-id="789cd-125">The simplest way is to declare a `Sub` procedure that does not take arguments or return a value.</span></span>  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   <span data-ttu-id="789cd-126">`Main`può inoltre restituire un `Integer` valore, il sistema operativo utilizza il codice di uscita per il programma.</span><span class="sxs-lookup"><span data-stu-id="789cd-126">`Main` can also return an `Integer` value, which the operating system uses as the exit code for your program.</span></span> <span data-ttu-id="789cd-127">Altri programmi è possano testare questo codice esaminando il valore di ERRORLEVEL di Windows.</span><span class="sxs-lookup"><span data-stu-id="789cd-127">Other programs can test this code by examining the Windows ERRORLEVEL value.</span></span> <span data-ttu-id="789cd-128">Per restituire un codice di uscita, è necessario dichiarare `Main` come un `Function` procedure anziché un `Sub` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="789cd-128">To return an exit code, you must declare `Main` as a `Function` procedure instead of a `Sub` procedure.</span></span>  
  
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
  
-   <span data-ttu-id="789cd-129">`Main`può anche richiedere un `String` matrice come argomento.</span><span class="sxs-lookup"><span data-stu-id="789cd-129">`Main` can also take a `String` array as an argument.</span></span> <span data-ttu-id="789cd-130">Ogni stringa della matrice contiene uno degli argomenti della riga di comando utilizzati per richiamare il programma.</span><span class="sxs-lookup"><span data-stu-id="789cd-130">Each string in the array contains one of the command-line arguments used to invoke your program.</span></span> <span data-ttu-id="789cd-131">È possibile eseguire azioni diverse a seconda di valori.</span><span class="sxs-lookup"><span data-stu-id="789cd-131">You can take different actions depending on their values.</span></span>  
  
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
  
-   <span data-ttu-id="789cd-132">È possibile dichiarare `Main` per esaminare gli argomenti della riga di comando, ma non restituisce un codice di uscita, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="789cd-132">You can declare `Main` to examine the command-line arguments but not return an exit code, as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="789cd-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="789cd-133">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
 <xref:System.Array.Length%2A>  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [<span data-ttu-id="789cd-134">Struttura di un programma Visual Basic</span><span class="sxs-lookup"><span data-stu-id="789cd-134">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [<span data-ttu-id="789cd-135">/main</span><span class="sxs-lookup"><span data-stu-id="789cd-135">/main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)  
 [<span data-ttu-id="789cd-136">Shared</span><span class="sxs-lookup"><span data-stu-id="789cd-136">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="789cd-137">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="789cd-137">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="789cd-138">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="789cd-138">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="789cd-139">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="789cd-139">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="789cd-140">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="789cd-140">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
