---
title: 'Procedura: Visualizzare gli argomenti della riga di comando - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 948ff6e752b3f5cce870b483340cbbf9f4e78b01
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607715"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="da32d-102">Procedura: Visualizzare gli argomenti della riga di comando (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="da32d-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="da32d-103">Gli argomenti specificati per un file eseguibile dalla riga di comando sono accessibili tramite un parametro facoltativo per `Main`.</span><span class="sxs-lookup"><span data-stu-id="da32d-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="da32d-104">Gli argomenti vengono specificati sotto forma di una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="da32d-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="da32d-105">Ogni elemento della matrice contiene un solo argomento.</span><span class="sxs-lookup"><span data-stu-id="da32d-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="da32d-106">Gli spazi vuoti tra gli argomenti vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="da32d-106">White-space between arguments is removed.</span></span> <span data-ttu-id="da32d-107">Si considerino ad esempio le chiamate seguenti della riga di comando di un file eseguibile fittizio:</span><span class="sxs-lookup"><span data-stu-id="da32d-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="da32d-108">Input riga di comando</span><span class="sxs-lookup"><span data-stu-id="da32d-108">Input on Command-line</span></span>|<span data-ttu-id="da32d-109">Matrice di stringhe passate a Main</span><span class="sxs-lookup"><span data-stu-id="da32d-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="da32d-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="da32d-110">**executable.exe a b c**</span></span>|<span data-ttu-id="da32d-111">"a"</span><span class="sxs-lookup"><span data-stu-id="da32d-111">"a"</span></span><br /><br /> <span data-ttu-id="da32d-112">"b"</span><span class="sxs-lookup"><span data-stu-id="da32d-112">"b"</span></span><br /><br /> <span data-ttu-id="da32d-113">"c"</span><span class="sxs-lookup"><span data-stu-id="da32d-113">"c"</span></span>|  
|<span data-ttu-id="da32d-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="da32d-114">**executable.exe one two**</span></span>|<span data-ttu-id="da32d-115">"one"</span><span class="sxs-lookup"><span data-stu-id="da32d-115">"one"</span></span><br /><br /> <span data-ttu-id="da32d-116">"two"</span><span class="sxs-lookup"><span data-stu-id="da32d-116">"two"</span></span>|  
|<span data-ttu-id="da32d-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="da32d-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="da32d-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="da32d-118">"one two"</span></span><br /><br /> <span data-ttu-id="da32d-119">"three"</span><span class="sxs-lookup"><span data-stu-id="da32d-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="da32d-120">Quando si esegue un'applicazione in Visual Studio, è possibile specificare argomenti della riga di comando nella [Pagina Debug, Progettazione progetti](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="da32d-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="da32d-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="da32d-121">Example</span></span>  
 <span data-ttu-id="da32d-122">In questo esempio vengono visualizzati gli argomenti della riga di comando passati a un'applicazione della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="da32d-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="da32d-123">L'output visualizzato è per la prima voce nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="da32d-123">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="da32d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da32d-124">See also</span></span>

- [<span data-ttu-id="da32d-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="da32d-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="da32d-126">Compilazione dalla riga di comando con csc.exe</span><span class="sxs-lookup"><span data-stu-id="da32d-126">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="da32d-127">Main() e argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="da32d-127">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)
- [<span data-ttu-id="da32d-128">Procedura: Accedere agli argomenti della riga di comando usando foreach</span><span class="sxs-lookup"><span data-stu-id="da32d-128">How to: Access Command-Line Arguments Using foreach</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)
- [<span data-ttu-id="da32d-129">Valori restituiti da Main()</span><span class="sxs-lookup"><span data-stu-id="da32d-129">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
