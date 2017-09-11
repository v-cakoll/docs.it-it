---
title: 'Procedura: accedere agli argomenti della riga di comando utilizzando foreach (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
caps.latest.revision: 15
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
ms.openlocfilehash: 766b5cd0879edec1dc409e07c4f62ee693fd615d
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a><span data-ttu-id="9c645-102">Procedura: accedere agli argomenti della riga di comando utilizzando foreach (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="9c645-102">How to: Access Command-Line Arguments Using foreach (C# Programming Guide)</span></span>
<span data-ttu-id="9c645-103">Un altro approccio per eseguire l'iterazione della matrice consiste nell'usare l'istruzione [foreach](../../../csharp/language-reference/keywords/foreach-in.md), come illustrato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="9c645-103">Another approach to iterating over the array is to use the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement as shown in this example.</span></span> <span data-ttu-id="9c645-104">L'istruzione `foreach` può essere usata per eseguire l'iterazione di una matrice, una classe di raccolte .NET Framework o qualsiasi classe o struct che implementa l'interfaccia <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="9c645-104">The `foreach` statement can be used to iterate over an array, a .NET Framework collection class, or any class or struct that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c645-105">Quando si esegue un'applicazione in Visual Studio, è possibile specificare argomenti della riga di comando nella [Pagina Debug, Progettazione progetti](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="9c645-105">When running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c645-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="9c645-106">Example</span></span>  
 <span data-ttu-id="9c645-107">In questo esempio viene illustrato come stampare gli argomenti della riga di comando usando `foreach`.</span><span class="sxs-lookup"><span data-stu-id="9c645-107">This example demonstrates how to print out the command line arguments using `foreach`.</span></span>  
  
 <span data-ttu-id="9c645-108">[!code-cs[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9c645-108">[!code-cs[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]</span></span>  
  
 <span data-ttu-id="9c645-109">[!code-cs[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9c645-109">[!code-cs[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c645-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c645-110">See Also</span></span>  
 <span data-ttu-id="9c645-111"><xref:System.Array></span><span class="sxs-lookup"><span data-stu-id="9c645-111"><xref:System.Array></span></span>   
 <span data-ttu-id="9c645-112"><xref:System.Collections></span><span class="sxs-lookup"><span data-stu-id="9c645-112"><xref:System.Collections></span></span>   
 <span data-ttu-id="9c645-113">[Compilazione dalla riga di comando con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span><span class="sxs-lookup"><span data-stu-id="9c645-113">[Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span></span>  
 <span data-ttu-id="9c645-114">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9c645-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9c645-115">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span><span class="sxs-lookup"><span data-stu-id="9c645-115">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span></span>  
 <span data-ttu-id="9c645-116">[Main() e argomenti della riga di comando](../../../csharp/programming-guide/main-and-command-args/index.md) </span><span class="sxs-lookup"><span data-stu-id="9c645-116">[Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) </span></span>  
 <span data-ttu-id="9c645-117">[Procedura: Visualizzare gli argomenti della riga di comando](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="9c645-117">[How to: Display Command Line Arguments](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md) </span></span>  
 [<span data-ttu-id="9c645-118">Valori restituiti da Main()</span><span class="sxs-lookup"><span data-stu-id="9c645-118">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)

