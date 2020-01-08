---
title: Come visualizzare gli argomenti della riga di C# comando-Guida alla programmazione
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 3ae2f65696c6661ab4f732b604267116996162b2
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635171"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="43b25-102">Come visualizzare gli argomenti della riga diC# comando (Guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="43b25-102">How to display command line arguments (C# Programming Guide)</span></span>
<span data-ttu-id="43b25-103">Gli argomenti specificati per un file eseguibile dalla riga di comando sono accessibili tramite un parametro facoltativo per `Main`.</span><span class="sxs-lookup"><span data-stu-id="43b25-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="43b25-104">Gli argomenti vengono specificati sotto forma di una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="43b25-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="43b25-105">Ogni elemento della matrice contiene un solo argomento.</span><span class="sxs-lookup"><span data-stu-id="43b25-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="43b25-106">Gli spazi vuoti tra gli argomenti vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="43b25-106">White-space between arguments is removed.</span></span> <span data-ttu-id="43b25-107">Si considerino ad esempio le chiamate seguenti della riga di comando di un file eseguibile fittizio:</span><span class="sxs-lookup"><span data-stu-id="43b25-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="43b25-108">Input riga di comando</span><span class="sxs-lookup"><span data-stu-id="43b25-108">Input on Command-line</span></span>|<span data-ttu-id="43b25-109">Matrice di stringhe passate a Main</span><span class="sxs-lookup"><span data-stu-id="43b25-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="43b25-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="43b25-110">**executable.exe a b c**</span></span>|<span data-ttu-id="43b25-111">"a"</span><span class="sxs-lookup"><span data-stu-id="43b25-111">"a"</span></span><br /><br /> <span data-ttu-id="43b25-112">"b"</span><span class="sxs-lookup"><span data-stu-id="43b25-112">"b"</span></span><br /><br /> <span data-ttu-id="43b25-113">"c"</span><span class="sxs-lookup"><span data-stu-id="43b25-113">"c"</span></span>|  
|<span data-ttu-id="43b25-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="43b25-114">**executable.exe one two**</span></span>|<span data-ttu-id="43b25-115">"one"</span><span class="sxs-lookup"><span data-stu-id="43b25-115">"one"</span></span><br /><br /> <span data-ttu-id="43b25-116">"two"</span><span class="sxs-lookup"><span data-stu-id="43b25-116">"two"</span></span>|  
|<span data-ttu-id="43b25-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="43b25-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="43b25-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="43b25-118">"one two"</span></span><br /><br /> <span data-ttu-id="43b25-119">"three"</span><span class="sxs-lookup"><span data-stu-id="43b25-119">"three"</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="43b25-120">Quando si esegue un'applicazione in Visual Studio, è possibile specificare argomenti della riga di comando nella [Pagina Debug, Progettazione progetti](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="43b25-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="43b25-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="43b25-121">Example</span></span>  
 <span data-ttu-id="43b25-122">In questo esempio vengono visualizzati gli argomenti della riga di comando passati a un'applicazione della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="43b25-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="43b25-123">L'output visualizzato è per la prima voce nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="43b25-123">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="43b25-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43b25-124">See also</span></span>

- [<span data-ttu-id="43b25-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="43b25-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="43b25-126">Compilazione dalla riga di comando con csc.exe</span><span class="sxs-lookup"><span data-stu-id="43b25-126">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="43b25-127">Main() e argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="43b25-127">Main() and Command-Line Arguments</span></span>](./index.md)
- [<span data-ttu-id="43b25-128">Valori restituiti da Main()</span><span class="sxs-lookup"><span data-stu-id="43b25-128">Main() Return Values</span></span>](./main-return-values.md)
