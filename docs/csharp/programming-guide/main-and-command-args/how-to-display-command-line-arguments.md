---
title: 'Procedura: visualizzare gli argomenti della riga di comando (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cf8a57cce252b3596f0a19c9df643427615467c6
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="44821-102">Procedura: visualizzare gli argomenti della riga di comando (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="44821-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="44821-103">Gli argomenti specificati per un file eseguibile dalla riga di comando sono accessibili tramite un parametro facoltativo per `Main`.</span><span class="sxs-lookup"><span data-stu-id="44821-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="44821-104">Gli argomenti vengono specificati sotto forma di una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="44821-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="44821-105">Ogni elemento della matrice contiene un solo argomento.</span><span class="sxs-lookup"><span data-stu-id="44821-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="44821-106">Gli spazi vuoti tra gli argomenti vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="44821-106">White-space between arguments is removed.</span></span> <span data-ttu-id="44821-107">Si considerino ad esempio le chiamate seguenti della riga di comando di un file eseguibile fittizio:</span><span class="sxs-lookup"><span data-stu-id="44821-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="44821-108">Input riga di comando</span><span class="sxs-lookup"><span data-stu-id="44821-108">Input on Command-line</span></span>|<span data-ttu-id="44821-109">Matrice di stringhe passate a Main</span><span class="sxs-lookup"><span data-stu-id="44821-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="44821-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="44821-110">**executable.exe a b c**</span></span>|<span data-ttu-id="44821-111">"a"</span><span class="sxs-lookup"><span data-stu-id="44821-111">"a"</span></span><br /><br /> <span data-ttu-id="44821-112">"b"</span><span class="sxs-lookup"><span data-stu-id="44821-112">"b"</span></span><br /><br /> <span data-ttu-id="44821-113">"c"</span><span class="sxs-lookup"><span data-stu-id="44821-113">"c"</span></span>|  
|<span data-ttu-id="44821-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="44821-114">**executable.exe one two**</span></span>|<span data-ttu-id="44821-115">"one"</span><span class="sxs-lookup"><span data-stu-id="44821-115">"one"</span></span><br /><br /> <span data-ttu-id="44821-116">"two"</span><span class="sxs-lookup"><span data-stu-id="44821-116">"two"</span></span>|  
|<span data-ttu-id="44821-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="44821-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="44821-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="44821-118">"one two"</span></span><br /><br /> <span data-ttu-id="44821-119">"three"</span><span class="sxs-lookup"><span data-stu-id="44821-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="44821-120">Quando si esegue un'applicazione in Visual Studio, è possibile specificare argomenti della riga di comando nella [Pagina Debug, Progettazione progetti](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="44821-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="44821-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="44821-121">Example</span></span>  
 <span data-ttu-id="44821-122">In questo esempio vengono visualizzati gli argomenti della riga di comando passati a un'applicazione della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="44821-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="44821-123">L'output visualizzato è per la prima voce nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="44821-123">The output shown is for the first entry in the table above.</span></span>  
  
 <span data-ttu-id="44821-124">[!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="44821-124">[!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44821-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44821-125">See Also</span></span>  
 <span data-ttu-id="44821-126">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="44821-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="44821-127">[Compilazione dalla riga di comando con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span><span class="sxs-lookup"><span data-stu-id="44821-127">[Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span></span>  
 <span data-ttu-id="44821-128">[Main() e argomenti della riga di comando](../../../csharp/programming-guide/main-and-command-args/index.md) </span><span class="sxs-lookup"><span data-stu-id="44821-128">[Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) </span></span>  
 <span data-ttu-id="44821-129">[Procedura: Accedere agli argomenti della riga di comando usando foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md) </span><span class="sxs-lookup"><span data-stu-id="44821-129">[How to: Access Command-Line Arguments Using foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md) </span></span>  
 [<span data-ttu-id="44821-130">Valori restituiti da Main()</span><span class="sxs-lookup"><span data-stu-id="44821-130">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)

