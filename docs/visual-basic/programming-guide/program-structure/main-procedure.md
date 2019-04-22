---
title: Routine Main in Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: 641edd2d0e0dde5f509c8fa77ccf65358fa76a31
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833672"
---
# <a name="main-procedure-in-visual-basic"></a><span data-ttu-id="87961-102">Routine Main in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="87961-102">Main Procedure in Visual Basic</span></span>
<span data-ttu-id="87961-103">Tutte le applicazioni Visual Basic devono contenere una routine denominata `Main`.</span><span class="sxs-lookup"><span data-stu-id="87961-103">Every Visual Basic application must contain a procedure called `Main`.</span></span> <span data-ttu-id="87961-104">Questa procedura viene usata come punto di partenza e controllo generale per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87961-104">This procedure serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="87961-105">Le chiamate di .NET Framework di `Main` procedure quando è stata caricata l'applicazione ed è pronto per passare il controllo ad esso.</span><span class="sxs-lookup"><span data-stu-id="87961-105">The .NET Framework calls your `Main` procedure when it has loaded your application and is ready to pass control to it.</span></span> <span data-ttu-id="87961-106">A meno che non si sta creando un'applicazione Windows Forms, è necessario scrivere il `Main` procedure per le applicazioni eseguite nel proprio.</span><span class="sxs-lookup"><span data-stu-id="87961-106">Unless you are creating a Windows Forms application, you must write the `Main` procedure for applications that run on their own.</span></span>  
  
 <span data-ttu-id="87961-107">`Main` contiene il codice che viene eseguito per primo.</span><span class="sxs-lookup"><span data-stu-id="87961-107">`Main` contains the code that runs first.</span></span> <span data-ttu-id="87961-108">In `Main`, è possibile determinare quale forma deve essere caricato prima all'avvio del programma, scoprire se una copia dell'applicazione è già in esecuzione nel sistema, stabilire un set di variabili per l'applicazione o aprire un database che richiede l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87961-108">In `Main`, you can determine which form is to be loaded first when the program starts, find out if a copy of your application is already running on the system, establish a set of variables for your application, or open a database that the application requires.</span></span>  
  
## <a name="requirements-for-the-main-procedure"></a><span data-ttu-id="87961-109">Requisiti per la procedura principale</span><span class="sxs-lookup"><span data-stu-id="87961-109">Requirements for the Main Procedure</span></span>  
 <span data-ttu-id="87961-110">Un file che viene eseguito in un proprio (in genere con estensione .exe) deve contenere un `Main` procedure.</span><span class="sxs-lookup"><span data-stu-id="87961-110">A file that runs on its own (usually with extension .exe) must contain a `Main` procedure.</span></span> <span data-ttu-id="87961-111">Una libreria (ad esempio con estensione dll) non viene eseguito in una proprio e non richiede un `Main` procedure.</span><span class="sxs-lookup"><span data-stu-id="87961-111">A library (for example with extension .dll) does not run on its own and does not require a `Main` procedure.</span></span> <span data-ttu-id="87961-112">I requisiti per i diversi tipi di progetti che è possibile creare sono come segue:</span><span class="sxs-lookup"><span data-stu-id="87961-112">The requirements for the different types of projects you can create are as follows:</span></span>  
  
-   <span data-ttu-id="87961-113">Applicazioni console eseguire propri, quindi è necessario specificare almeno uno `Main` procedure.</span><span class="sxs-lookup"><span data-stu-id="87961-113">Console applications run on their own, and you must supply at least one `Main` procedure.</span></span> <span data-ttu-id="87961-114">.</span><span class="sxs-lookup"><span data-stu-id="87961-114">.</span></span>  
  
-   <span data-ttu-id="87961-115">Applicazioni di Windows Form eseguire propri.</span><span class="sxs-lookup"><span data-stu-id="87961-115">Windows Forms applications run on their own.</span></span> <span data-ttu-id="87961-116">Tuttavia, il compilatore Visual Basic genera automaticamente un `Main` procedura ad un'applicazione e non si è necessario scrivere uno.</span><span class="sxs-lookup"><span data-stu-id="87961-116">However, the Visual Basic compiler automatically generates a `Main` procedure in such an application, and you do not need to write one.</span></span>  
  
-   <span data-ttu-id="87961-117">Librerie di classi non richiedono un `Main` procedure.</span><span class="sxs-lookup"><span data-stu-id="87961-117">Class libraries do not require a `Main` procedure.</span></span> <span data-ttu-id="87961-118">Ad esempio librerie di controlli di Windows e le librerie di controlli Web.</span><span class="sxs-lookup"><span data-stu-id="87961-118">These include Windows Control Libraries and Web Control Libraries.</span></span> <span data-ttu-id="87961-119">Le applicazioni Web vengono distribuite come librerie di classi.</span><span class="sxs-lookup"><span data-stu-id="87961-119">Web applications are deployed as class libraries.</span></span>  
  
## <a name="declaring-the-main-procedure"></a><span data-ttu-id="87961-120">Dichiarazione della routine Main</span><span class="sxs-lookup"><span data-stu-id="87961-120">Declaring the Main Procedure</span></span>  
 <span data-ttu-id="87961-121">Sono disponibili quattro modi per dichiarare il `Main` procedure.</span><span class="sxs-lookup"><span data-stu-id="87961-121">There are four ways to declare the `Main` procedure.</span></span> <span data-ttu-id="87961-122">O non può accettare argomenti e può restituire un valore o non.</span><span class="sxs-lookup"><span data-stu-id="87961-122">It can take arguments or not, and it can return a value or not.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87961-123">Se si dichiara `Main` in una classe, è necessario usare il `Shared` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="87961-123">If you declare `Main` in a class, you must use the `Shared` keyword.</span></span> <span data-ttu-id="87961-124">In un modulo `Main` non dovrà essere `Shared`.</span><span class="sxs-lookup"><span data-stu-id="87961-124">In a module, `Main` does not need to be `Shared`.</span></span>  
  
-   <span data-ttu-id="87961-125">Il modo più semplice consiste nel dichiarare una `Sub` routine che non accetta argomenti e restituiscono un valore.</span><span class="sxs-lookup"><span data-stu-id="87961-125">The simplest way is to declare a `Sub` procedure that does not take arguments or return a value.</span></span>  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   <span data-ttu-id="87961-126">`Main` può inoltre restituire un `Integer` valore, che usa il sistema operativo come il codice di uscita per il programma.</span><span class="sxs-lookup"><span data-stu-id="87961-126">`Main` can also return an `Integer` value, which the operating system uses as the exit code for your program.</span></span> <span data-ttu-id="87961-127">Altri programmi è possono testare questo codice esaminando il valore di ERRORLEVEL di Windows.</span><span class="sxs-lookup"><span data-stu-id="87961-127">Other programs can test this code by examining the Windows ERRORLEVEL value.</span></span> <span data-ttu-id="87961-128">Per restituire un codice di uscita, è necessario dichiarare `Main` come un `Function` procedure anziché un `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="87961-128">To return an exit code, you must declare `Main` as a `Function` procedure instead of a `Sub` procedure.</span></span>  
  
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
  
-   <span data-ttu-id="87961-129">`Main` può inoltre assumere un `String` matrice come argomento.</span><span class="sxs-lookup"><span data-stu-id="87961-129">`Main` can also take a `String` array as an argument.</span></span> <span data-ttu-id="87961-130">Ogni stringa nella matrice contiene uno degli argomenti della riga di comando usati per richiamare il programma.</span><span class="sxs-lookup"><span data-stu-id="87961-130">Each string in the array contains one of the command-line arguments used to invoke your program.</span></span> <span data-ttu-id="87961-131">È possibile eseguire azioni diverse a seconda della loro valori.</span><span class="sxs-lookup"><span data-stu-id="87961-131">You can take different actions depending on their values.</span></span>  
  
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
  
-   <span data-ttu-id="87961-132">È possibile dichiarare `Main` per esaminare gli argomenti della riga di comando, ma non restituisce un codice di uscita, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="87961-132">You can declare `Main` to examine the command-line arguments but not return an exit code, as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="87961-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87961-133">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="87961-134">Struttura di un programma Visual Basic</span><span class="sxs-lookup"><span data-stu-id="87961-134">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="87961-135">/main</span><span class="sxs-lookup"><span data-stu-id="87961-135">/main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="87961-136">Shared</span><span class="sxs-lookup"><span data-stu-id="87961-136">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="87961-137">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="87961-137">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="87961-138">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="87961-138">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="87961-139">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="87961-139">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="87961-140">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="87961-140">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
