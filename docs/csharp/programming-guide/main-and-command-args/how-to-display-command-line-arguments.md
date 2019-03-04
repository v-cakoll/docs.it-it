---
title: 'Procedura: Visualizzare gli argomenti della riga di comando - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: b7018afa1272f4ae092863de6b7f9ef783001244
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965592"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="6aab9-102">Procedura: Visualizzare gli argomenti della riga di comando (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="6aab9-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="6aab9-103">Gli argomenti specificati per un file eseguibile dalla riga di comando sono accessibili tramite un parametro facoltativo per `Main`.</span><span class="sxs-lookup"><span data-stu-id="6aab9-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="6aab9-104">Gli argomenti vengono specificati sotto forma di una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="6aab9-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="6aab9-105">Ogni elemento della matrice contiene un solo argomento.</span><span class="sxs-lookup"><span data-stu-id="6aab9-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="6aab9-106">Gli spazi vuoti tra gli argomenti vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="6aab9-106">White-space between arguments is removed.</span></span> <span data-ttu-id="6aab9-107">Si considerino ad esempio le chiamate seguenti della riga di comando di un file eseguibile fittizio:</span><span class="sxs-lookup"><span data-stu-id="6aab9-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="6aab9-108">Input riga di comando</span><span class="sxs-lookup"><span data-stu-id="6aab9-108">Input on Command-line</span></span>|<span data-ttu-id="6aab9-109">Matrice di stringhe passate a Main</span><span class="sxs-lookup"><span data-stu-id="6aab9-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="6aab9-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="6aab9-110">**executable.exe a b c**</span></span>|<span data-ttu-id="6aab9-111">"a"</span><span class="sxs-lookup"><span data-stu-id="6aab9-111">"a"</span></span><br /><br /> <span data-ttu-id="6aab9-112">"b"</span><span class="sxs-lookup"><span data-stu-id="6aab9-112">"b"</span></span><br /><br /> <span data-ttu-id="6aab9-113">"c"</span><span class="sxs-lookup"><span data-stu-id="6aab9-113">"c"</span></span>|  
|<span data-ttu-id="6aab9-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="6aab9-114">**executable.exe one two**</span></span>|<span data-ttu-id="6aab9-115">"one"</span><span class="sxs-lookup"><span data-stu-id="6aab9-115">"one"</span></span><br /><br /> <span data-ttu-id="6aab9-116">"two"</span><span class="sxs-lookup"><span data-stu-id="6aab9-116">"two"</span></span>|  
|<span data-ttu-id="6aab9-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="6aab9-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="6aab9-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="6aab9-118">"one two"</span></span><br /><br /> <span data-ttu-id="6aab9-119">"three"</span><span class="sxs-lookup"><span data-stu-id="6aab9-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="6aab9-120">Quando si esegue un'applicazione in Visual Studio, è possibile specificare argomenti della riga di comando nella [Pagina Debug, Progettazione progetti](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="6aab9-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6aab9-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="6aab9-121">Example</span></span>  
 <span data-ttu-id="6aab9-122">In questo esempio vengono visualizzati gli argomenti della riga di comando passati a un'applicazione della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="6aab9-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="6aab9-123">L'output visualizzato è per la prima voce nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="6aab9-123">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="6aab9-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6aab9-124">See also</span></span>

- [<span data-ttu-id="6aab9-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="6aab9-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="6aab9-126">Compilazione dalla riga di comando con csc.exe</span><span class="sxs-lookup"><span data-stu-id="6aab9-126">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="6aab9-127">Main() e argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="6aab9-127">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)
- [<span data-ttu-id="6aab9-128">Procedura: Accedere agli argomenti della riga di comando usando foreach</span><span class="sxs-lookup"><span data-stu-id="6aab9-128">How to: Access Command-Line Arguments Using foreach</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)
- [<span data-ttu-id="6aab9-129">Valori restituiti da Main()</span><span class="sxs-lookup"><span data-stu-id="6aab9-129">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
