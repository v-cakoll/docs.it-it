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
# <a name="main-procedure-in-visual-basic"></a><span data-ttu-id="f37a4-102">Routine Main in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f37a4-102">Main Procedure in Visual Basic</span></span>
<span data-ttu-id="f37a4-103">Ogni applicazione Visual Basic deve contenere una procedura denominata `Main` .</span><span class="sxs-lookup"><span data-stu-id="f37a4-103">Every Visual Basic application must contain a procedure called `Main`.</span></span> <span data-ttu-id="f37a4-104">Questa procedura funge da punto di partenza e controllo generale per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f37a4-104">This procedure serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="f37a4-105">Il .NET Framework chiama la `Main` procedura quando ha caricato l'applicazione ed è pronta per passare il controllo.</span><span class="sxs-lookup"><span data-stu-id="f37a4-105">The .NET Framework calls your `Main` procedure when it has loaded your application and is ready to pass control to it.</span></span> <span data-ttu-id="f37a4-106">A meno che non si stia creando una Windows Forms Application, è necessario scrivere la `Main` procedura per le applicazioni che vengono eseguite autonomamente.</span><span class="sxs-lookup"><span data-stu-id="f37a4-106">Unless you are creating a Windows Forms application, you must write the `Main` procedure for applications that run on their own.</span></span>

 <span data-ttu-id="f37a4-107">`Main`contiene il codice che viene eseguito per primo.</span><span class="sxs-lookup"><span data-stu-id="f37a4-107">`Main` contains the code that runs first.</span></span> <span data-ttu-id="f37a4-108">In `Main` è possibile determinare il modulo da caricare per primo all'avvio del programma, verificare se una copia dell'applicazione è già in esecuzione nel sistema, stabilire un set di variabili per l'applicazione o aprire un database necessario per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f37a4-108">In `Main`, you can determine which form is to be loaded first when the program starts, find out if a copy of your application is already running on the system, establish a set of variables for your application, or open a database that the application requires.</span></span>

## <a name="requirements-for-the-main-procedure"></a><span data-ttu-id="f37a4-109">Requisiti per la procedura principale</span><span class="sxs-lookup"><span data-stu-id="f37a4-109">Requirements for the Main Procedure</span></span>
 <span data-ttu-id="f37a4-110">Un file che viene eseguito autonomamente, in genere con estensione exe, deve contenere una `Main` routine.</span><span class="sxs-lookup"><span data-stu-id="f37a4-110">A file that runs on its own (usually with extension .exe) must contain a `Main` procedure.</span></span> <span data-ttu-id="f37a4-111">Una libreria, ad esempio con estensione dll, non viene eseguita autonomamente e non richiede una `Main` procedura.</span><span class="sxs-lookup"><span data-stu-id="f37a4-111">A library (for example with extension .dll) does not run on its own and does not require a `Main` procedure.</span></span> <span data-ttu-id="f37a4-112">I requisiti per i diversi tipi di progetti che è possibile creare sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="f37a4-112">The requirements for the different types of projects you can create are as follows:</span></span>

- <span data-ttu-id="f37a4-113">Le applicazioni console vengono eseguite autonomamente ed è necessario fornire almeno una `Main` procedura.</span><span class="sxs-lookup"><span data-stu-id="f37a4-113">Console applications run on their own, and you must supply at least one `Main` procedure.</span></span>

- <span data-ttu-id="f37a4-114">Windows Forms le applicazioni vengono eseguite autonomamente.</span><span class="sxs-lookup"><span data-stu-id="f37a4-114">Windows Forms applications run on their own.</span></span> <span data-ttu-id="f37a4-115">Tuttavia, il compilatore Visual Basic genera automaticamente una `Main` procedura in tale applicazione e non è necessario scriverne una.</span><span class="sxs-lookup"><span data-stu-id="f37a4-115">However, the Visual Basic compiler automatically generates a `Main` procedure in such an application, and you do not need to write one.</span></span>

- <span data-ttu-id="f37a4-116">Le librerie di classi non richiedono una `Main` procedura.</span><span class="sxs-lookup"><span data-stu-id="f37a4-116">Class libraries do not require a `Main` procedure.</span></span> <span data-ttu-id="f37a4-117">Sono incluse le librerie di controlli Windows e le librerie di controlli Web.</span><span class="sxs-lookup"><span data-stu-id="f37a4-117">These include Windows Control Libraries and Web Control Libraries.</span></span> <span data-ttu-id="f37a4-118">Le applicazioni Web vengono distribuite come librerie di classi.</span><span class="sxs-lookup"><span data-stu-id="f37a4-118">Web applications are deployed as class libraries.</span></span>

## <a name="declaring-the-main-procedure"></a><span data-ttu-id="f37a4-119">Dichiarazione della routine Main</span><span class="sxs-lookup"><span data-stu-id="f37a4-119">Declaring the Main Procedure</span></span>
 <span data-ttu-id="f37a4-120">Esistono quattro modi per dichiarare la `Main` procedura.</span><span class="sxs-lookup"><span data-stu-id="f37a4-120">There are four ways to declare the `Main` procedure.</span></span> <span data-ttu-id="f37a4-121">Può assumere o meno argomenti e può restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="f37a4-121">It can take arguments or not, and it can return a value or not.</span></span>

> [!NOTE]
> <span data-ttu-id="f37a4-122">Se si dichiara `Main` in una classe, è necessario usare la `Shared` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="f37a4-122">If you declare `Main` in a class, you must use the `Shared` keyword.</span></span> <span data-ttu-id="f37a4-123">In un modulo `Main` non è necessario che sia `Shared` .</span><span class="sxs-lookup"><span data-stu-id="f37a4-123">In a module, `Main` does not need to be `Shared`.</span></span>

- <span data-ttu-id="f37a4-124">Il modo più semplice consiste nel dichiarare una `Sub` routine che non accetta argomenti o restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="f37a4-124">The simplest way is to declare a `Sub` procedure that does not take arguments or return a value.</span></span>

    ```vb
    Module mainModule
        Sub Main()
            MsgBox("The Main procedure is starting the application.")
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```

- <span data-ttu-id="f37a4-125">`Main`può inoltre restituire un `Integer` valore, che viene utilizzato dal sistema operativo come codice di uscita per il programma.</span><span class="sxs-lookup"><span data-stu-id="f37a4-125">`Main` can also return an `Integer` value, which the operating system uses as the exit code for your program.</span></span> <span data-ttu-id="f37a4-126">Altri programmi possono testare questo codice esaminando il valore ERRORLEVEL di Windows.</span><span class="sxs-lookup"><span data-stu-id="f37a4-126">Other programs can test this code by examining the Windows ERRORLEVEL value.</span></span> <span data-ttu-id="f37a4-127">Per restituire un codice di uscita, è necessario dichiarare `Main` come `Function` routine anziché come `Sub` routine.</span><span class="sxs-lookup"><span data-stu-id="f37a4-127">To return an exit code, you must declare `Main` as a `Function` procedure instead of a `Sub` procedure.</span></span>

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

- <span data-ttu-id="f37a4-128">`Main`può inoltre assumere una `String` matrice come argomento.</span><span class="sxs-lookup"><span data-stu-id="f37a4-128">`Main` can also take a `String` array as an argument.</span></span> <span data-ttu-id="f37a4-129">Ogni stringa della matrice contiene uno degli argomenti della riga di comando usati per richiamare il programma.</span><span class="sxs-lookup"><span data-stu-id="f37a4-129">Each string in the array contains one of the command-line arguments used to invoke your program.</span></span> <span data-ttu-id="f37a4-130">È possibile eseguire azioni diverse a seconda dei rispettivi valori.</span><span class="sxs-lookup"><span data-stu-id="f37a4-130">You can take different actions depending on their values.</span></span>

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

- <span data-ttu-id="f37a4-131">È possibile dichiarare `Main` per esaminare gli argomenti della riga di comando, ma non per restituire un codice di uscita, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f37a4-131">You can declare `Main` to examine the command-line arguments but not return an exit code, as follows.</span></span>

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
  
## <a name="see-also"></a><span data-ttu-id="f37a4-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f37a4-132">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="f37a4-133">Struttura di un programma Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f37a4-133">Structure of a Visual Basic Program</span></span>](structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="f37a4-134">-main</span><span class="sxs-lookup"><span data-stu-id="f37a4-134">-main</span></span>](../../reference/command-line-compiler/main.md)
- [<span data-ttu-id="f37a4-135">Condivisa</span><span class="sxs-lookup"><span data-stu-id="f37a4-135">Shared</span></span>](../../language-reference/modifiers/shared.md)
- [<span data-ttu-id="f37a4-136">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="f37a4-136">Sub Statement</span></span>](../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="f37a4-137">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="f37a4-137">Function Statement</span></span>](../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="f37a4-138">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="f37a4-138">Integer Data Type</span></span>](../../language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="f37a4-139">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="f37a4-139">String Data Type</span></span>](../../language-reference/data-types/string-data-type.md)
