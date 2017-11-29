---
title: '&lt;list&gt; (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6d997f3692d21959daa8eaec9eeeac8c0a1dc9bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltlistgt-c-programming-guide"></a><span data-ttu-id="329a9-102">&lt;list&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="329a9-102">&lt;list&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="329a9-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="329a9-103">Syntax</span></span>  
  
```xml  
<list type="bullet" | "number" | "table">  
    <listheader>  
        <term>term</term>  
        <description>description</description>  
    </listheader>  
    <item>  
        <term>term</term>  
        <description>description</description>  
    </item>  
</list>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="329a9-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="329a9-104">Parameters</span></span>  
 `term`  
 <span data-ttu-id="329a9-105">Termine da definire, che verrà definito in `description`.</span><span class="sxs-lookup"><span data-stu-id="329a9-105">A term to define, which will be defined in `description`.</span></span>  
  
 `description`  
 <span data-ttu-id="329a9-106">Elemento di un elenco puntato o numerato oppure la definizione di un `term`.</span><span class="sxs-lookup"><span data-stu-id="329a9-106">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="329a9-107">Note</span><span class="sxs-lookup"><span data-stu-id="329a9-107">Remarks</span></span>  
 <span data-ttu-id="329a9-108">Il blocco \<listheader> viene usato per definire la riga di intestazione di una tabella o di un elenco di definizioni.</span><span class="sxs-lookup"><span data-stu-id="329a9-108">The \<listheader> block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="329a9-109">Per definire una tabella, è sufficiente specificare una voce per il termine nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="329a9-109">When defining a table, you only need to supply an entry for term in the heading.</span></span>  
  
 <span data-ttu-id="329a9-110">Ogni elemento dell'elenco viene specificato tramite un blocco \<item>.</span><span class="sxs-lookup"><span data-stu-id="329a9-110">Each item in the list is specified with an \<item> block.</span></span> <span data-ttu-id="329a9-111">Quando si crea un elenco di definizioni, è necessario specificare sia `term` che `description`.</span><span class="sxs-lookup"><span data-stu-id="329a9-111">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="329a9-112">Per le tabelle e gli elenchi puntati o numerati, tuttavia, è sufficiente fornire una voce per `description`.</span><span class="sxs-lookup"><span data-stu-id="329a9-112">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="329a9-113">Gli elenchi e le tabelle possono contenere un numero qualsiasi di blocchi \<item>.</span><span class="sxs-lookup"><span data-stu-id="329a9-113">A list or table can have as many \<item> blocks as needed.</span></span>  
  
 <span data-ttu-id="329a9-114">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="329a9-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="329a9-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="329a9-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="329a9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="329a9-116">See Also</span></span>  
 [<span data-ttu-id="329a9-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="329a9-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="329a9-118">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="329a9-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
