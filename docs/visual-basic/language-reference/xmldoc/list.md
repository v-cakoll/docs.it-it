---
title: <list> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
ms.openlocfilehash: 522450e4efcecaf74968ddb492b536aa98dc0b13
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260290"
---
# <a name="list-visual-basic"></a><span data-ttu-id="19604-102">\<list> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19604-102">\<list> (Visual Basic)</span></span>
<span data-ttu-id="19604-103">Definisce un elenco o una tabella.</span><span class="sxs-lookup"><span data-stu-id="19604-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19604-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19604-104">Syntax</span></span>  
  
```xml  
<list type="type">  
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
  
#### <a name="parameters"></a><span data-ttu-id="19604-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="19604-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="19604-106">Il tipo dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="19604-106">The type of the list.</span></span> <span data-ttu-id="19604-107">Deve essere un "punto elenco" per un elenco puntato, "number" per un elenco numerato o "table" per una tabella a due colonne.</span><span class="sxs-lookup"><span data-stu-id="19604-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="19604-108">Usato solo `type` è "table".</span><span class="sxs-lookup"><span data-stu-id="19604-108">Only used when `type` is "table."</span></span> <span data-ttu-id="19604-109">Termine da definire, che viene definito nel tag di descrizione.</span><span class="sxs-lookup"><span data-stu-id="19604-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="19604-110">Quando `type` è "bullet" o "number", `description` è un elemento nell'elenco quando `type` è "table" `description` è la definizione di `term`.</span><span class="sxs-lookup"><span data-stu-id="19604-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19604-111">Note</span><span class="sxs-lookup"><span data-stu-id="19604-111">Remarks</span></span>  
 <span data-ttu-id="19604-112">Il `<listheader>` blocco definisce l'intestazione di tabella o una definizione elenco.</span><span class="sxs-lookup"><span data-stu-id="19604-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="19604-113">Quando si definisce una tabella, è sufficiente fornire una voce per `term` nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="19604-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="19604-114">Ogni elemento nell'elenco viene specificato con un `<item>` blocco.</span><span class="sxs-lookup"><span data-stu-id="19604-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="19604-115">Quando si crea un elenco di definizioni, è necessario specificare entrambe `term` e `description`.</span><span class="sxs-lookup"><span data-stu-id="19604-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="19604-116">Tuttavia, per una tabella, elenco puntato o numerato, è sufficiente fornire una voce per `description`.</span><span class="sxs-lookup"><span data-stu-id="19604-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="19604-117">Un elenco o una tabella può avere un numero `<item>` blocca in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="19604-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="19604-118">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="19604-118">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19604-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="19604-119">Example</span></span>  
 <span data-ttu-id="19604-120">Questo esempio viene usato il `<list>` tag per definire un elenco puntato nella sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="19604-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="19604-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19604-121">See also</span></span>
- [<span data-ttu-id="19604-122">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="19604-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
