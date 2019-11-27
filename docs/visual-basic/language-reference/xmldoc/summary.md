---
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 3bc4393d2fa14f804c6383780e238b1ac2610a94
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352206"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="5bf88-101">> Riepilogo \<(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5bf88-101">\<summary> (Visual Basic)</span></span>
<span data-ttu-id="5bf88-102">Specifica il riepilogo del membro.</span><span class="sxs-lookup"><span data-stu-id="5bf88-102">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bf88-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5bf88-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bf88-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="5bf88-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="5bf88-105">Un riepilogo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="5bf88-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bf88-106">Note</span><span class="sxs-lookup"><span data-stu-id="5bf88-106">Remarks</span></span>  
 <span data-ttu-id="5bf88-107">Usare il tag `<summary>` per descrivere un tipo o un membro del tipo.</span><span class="sxs-lookup"><span data-stu-id="5bf88-107">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="5bf88-108">Utilizzare [ \<osservazioni >](../../../visual-basic/language-reference/xmldoc/remarks.md) per aggiungere informazioni supplementari alla descrizione di un tipo.</span><span class="sxs-lookup"><span data-stu-id="5bf88-108">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="5bf88-109">Il testo per il tag `<summary>` è l'unica fonte di informazioni sul tipo in IntelliSense e viene visualizzato anche nel Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="5bf88-109">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="5bf88-110">Per informazioni sulla Visualizzatore oggetti, vedere [visualizzazione della struttura del codice](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="5bf88-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="5bf88-111">Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="5bf88-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bf88-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="5bf88-112">Example</span></span>  
 <span data-ttu-id="5bf88-113">Questo esempio usa il tag `<summary>` per descrivere il metodo `ResetCounter` e `Counter` proprietà.</span><span class="sxs-lookup"><span data-stu-id="5bf88-113">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5bf88-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bf88-114">See also</span></span>

- [<span data-ttu-id="5bf88-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="5bf88-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
