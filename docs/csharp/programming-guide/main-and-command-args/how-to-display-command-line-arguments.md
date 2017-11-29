---
title: 'Procedura: visualizzare gli argomenti della riga di comando (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f6ae495eef227c6e4d9fb9ca0d4d0c031163fd52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="726fd-102">Procedura: visualizzare gli argomenti della riga di comando (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="726fd-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="726fd-103">Gli argomenti specificati per un file eseguibile dalla riga di comando sono accessibili tramite un parametro facoltativo per `Main`.</span><span class="sxs-lookup"><span data-stu-id="726fd-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="726fd-104">Gli argomenti vengono specificati sotto forma di una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="726fd-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="726fd-105">Ogni elemento della matrice contiene un solo argomento.</span><span class="sxs-lookup"><span data-stu-id="726fd-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="726fd-106">Gli spazi vuoti tra gli argomenti vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="726fd-106">White-space between arguments is removed.</span></span> <span data-ttu-id="726fd-107">Si considerino ad esempio le chiamate seguenti della riga di comando di un file eseguibile fittizio:</span><span class="sxs-lookup"><span data-stu-id="726fd-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="726fd-108">Input riga di comando</span><span class="sxs-lookup"><span data-stu-id="726fd-108">Input on Command-line</span></span>|<span data-ttu-id="726fd-109">Matrice di stringhe passate a Main</span><span class="sxs-lookup"><span data-stu-id="726fd-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="726fd-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="726fd-110">**executable.exe a b c**</span></span>|<span data-ttu-id="726fd-111">"a"</span><span class="sxs-lookup"><span data-stu-id="726fd-111">"a"</span></span><br /><br /> <span data-ttu-id="726fd-112">"b"</span><span class="sxs-lookup"><span data-stu-id="726fd-112">"b"</span></span><br /><br /> <span data-ttu-id="726fd-113">"c"</span><span class="sxs-lookup"><span data-stu-id="726fd-113">"c"</span></span>|  
|<span data-ttu-id="726fd-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="726fd-114">**executable.exe one two**</span></span>|<span data-ttu-id="726fd-115">"one"</span><span class="sxs-lookup"><span data-stu-id="726fd-115">"one"</span></span><br /><br /> <span data-ttu-id="726fd-116">"two"</span><span class="sxs-lookup"><span data-stu-id="726fd-116">"two"</span></span>|  
|<span data-ttu-id="726fd-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="726fd-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="726fd-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="726fd-118">"one two"</span></span><br /><br /> <span data-ttu-id="726fd-119">"three"</span><span class="sxs-lookup"><span data-stu-id="726fd-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="726fd-120">Quando si esegue un'applicazione in Visual Studio, è possibile specificare argomenti della riga di comando nella [Pagina Debug, Progettazione progetti](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="726fd-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="726fd-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="726fd-121">Example</span></span>  
 <span data-ttu-id="726fd-122">In questo esempio vengono visualizzati gli argomenti della riga di comando passati a un'applicazione della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="726fd-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="726fd-123">L'output visualizzato è per la prima voce nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="726fd-123">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="726fd-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="726fd-124">See Also</span></span>  
 [<span data-ttu-id="726fd-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="726fd-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="726fd-126">Compilazione dalla riga di comando con csc.exe</span><span class="sxs-lookup"><span data-stu-id="726fd-126">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 [<span data-ttu-id="726fd-127">Main() e argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="726fd-127">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [<span data-ttu-id="726fd-128">Procedura: Accedere agli argomenti della riga di comando usando foreach</span><span class="sxs-lookup"><span data-stu-id="726fd-128">How to: Access Command-Line Arguments Using foreach</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
 [<span data-ttu-id="726fd-129">Valori restituiti da Main()</span><span class="sxs-lookup"><span data-stu-id="726fd-129">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
