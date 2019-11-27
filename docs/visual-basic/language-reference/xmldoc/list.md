---
title: <list>
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
ms.openlocfilehash: db5c571d2f2c59419c886f6596f4e4dbd30d7baf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352314"
---
# <a name="list-visual-basic"></a><span data-ttu-id="e8a89-101">elenco di \<> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8a89-101">\<list> (Visual Basic)</span></span>
<span data-ttu-id="e8a89-102">Definisce un elenco o una tabella.</span><span class="sxs-lookup"><span data-stu-id="e8a89-102">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8a89-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8a89-103">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e8a89-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8a89-104">Parameters</span></span>  
 `type`  
 <span data-ttu-id="e8a89-105">Tipo dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e8a89-105">The type of the list.</span></span> <span data-ttu-id="e8a89-106">Deve essere un "Bullet" per un elenco puntato, "Number" per un elenco numerato o "Table" per una tabella a due colonne.</span><span class="sxs-lookup"><span data-stu-id="e8a89-106">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="e8a89-107">Utilizzato solo quando `type` è "Table".</span><span class="sxs-lookup"><span data-stu-id="e8a89-107">Only used when `type` is "table."</span></span> <span data-ttu-id="e8a89-108">Termine da definire, definito nel tag Description.</span><span class="sxs-lookup"><span data-stu-id="e8a89-108">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="e8a89-109">Quando `type` è "Bullet" o "Number", `description` è un elemento nell'elenco quando `type` è "Table" `description` è la definizione di `term`.</span><span class="sxs-lookup"><span data-stu-id="e8a89-109">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8a89-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e8a89-110">Remarks</span></span>  
 <span data-ttu-id="e8a89-111">Il blocco `<listheader>` definisce l'intestazione di un elenco di tabelle o di definizioni.</span><span class="sxs-lookup"><span data-stu-id="e8a89-111">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="e8a89-112">Quando si definisce una tabella, è necessario specificare solo una voce per `term` nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="e8a89-112">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="e8a89-113">Ogni elemento nell'elenco viene specificato con un blocco `<item>`.</span><span class="sxs-lookup"><span data-stu-id="e8a89-113">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="e8a89-114">Quando si crea un elenco di definizioni, è necessario specificare sia `term` sia `description`.</span><span class="sxs-lookup"><span data-stu-id="e8a89-114">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="e8a89-115">Tuttavia, per una tabella, un elenco puntato o un elenco numerato, è necessario specificare solo una voce per `description`.</span><span class="sxs-lookup"><span data-stu-id="e8a89-115">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="e8a89-116">Un elenco o una tabella può contenere il numero di blocchi di `<item>` necessari.</span><span class="sxs-lookup"><span data-stu-id="e8a89-116">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="e8a89-117">Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="e8a89-117">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8a89-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8a89-118">Example</span></span>  
 <span data-ttu-id="e8a89-119">Questo esempio usa il tag `<list>` per definire un elenco puntato nella sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="e8a89-119">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="e8a89-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8a89-120">See also</span></span>

- [<span data-ttu-id="e8a89-121">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="e8a89-121">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
