---
title: '&lt;riepilogo&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 5ef9b7a98503ff36174de4418ca7d599c365f5aa
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45593780"
---
# <a name="ltsummarygt-visual-basic"></a><span data-ttu-id="11500-102">&lt;riepilogo&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11500-102">&lt;summary&gt; (Visual Basic)</span></span>
<span data-ttu-id="11500-103">Specifica il riepilogo del membro.</span><span class="sxs-lookup"><span data-stu-id="11500-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11500-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11500-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11500-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="11500-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="11500-106">Un riepilogo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="11500-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11500-107">Note</span><span class="sxs-lookup"><span data-stu-id="11500-107">Remarks</span></span>  
 <span data-ttu-id="11500-108">Usare il `<summary>` tag per descrivere un tipo o un membro del tipo.</span><span class="sxs-lookup"><span data-stu-id="11500-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="11500-109">Utilizzare [ \<osservazioni >](../../../visual-basic/language-reference/xmldoc/remarks.md) per aggiungere informazioni supplementari alla descrizione di un tipo.</span><span class="sxs-lookup"><span data-stu-id="11500-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="11500-110">Il testo per il `<summary>` tag è l'unica fonte di informazioni sul tipo in IntelliSense e viene anche visualizzato nel Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="11500-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="11500-111">Per informazioni sul Visualizzatore oggetti, vedere [visualizzazione della struttura del codice](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="11500-111">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="11500-112">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="11500-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11500-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="11500-113">Example</span></span>  
 <span data-ttu-id="11500-114">Questo esempio Usa la `<summary>` tag per descrivere le `ResetCounter` metodo e `Counter` proprietà.</span><span class="sxs-lookup"><span data-stu-id="11500-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="11500-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11500-115">See Also</span></span>  
 [<span data-ttu-id="11500-116">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="11500-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
