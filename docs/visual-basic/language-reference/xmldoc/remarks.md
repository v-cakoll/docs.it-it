---
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: c57ddb870192bd94301f99eb71ad29526e8efc28
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400021"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="00f95-101">\<remarks> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00f95-101">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="00f95-102">Specifica una sezione di osservazioni per il membro.</span><span class="sxs-lookup"><span data-stu-id="00f95-102">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00f95-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00f95-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="00f95-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="00f95-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="00f95-105">Descrizione del membro.</span><span class="sxs-lookup"><span data-stu-id="00f95-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00f95-106">Commenti</span><span class="sxs-lookup"><span data-stu-id="00f95-106">Remarks</span></span>  
 <span data-ttu-id="00f95-107">Usare il `<remarks>` tag per aggiungere informazioni su un tipo, integrando le informazioni specificate con [\<summary>](summary.md) .</span><span class="sxs-lookup"><span data-stu-id="00f95-107">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](summary.md).</span></span>  
  
 <span data-ttu-id="00f95-108">Queste informazioni vengono visualizzate nel Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="00f95-108">This information appears in the Object Browser.</span></span> <span data-ttu-id="00f95-109">Per informazioni sulla Visualizzatore oggetti, vedere [visualizzazione della struttura del codice](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="00f95-109">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="00f95-110">Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="00f95-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00f95-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="00f95-111">Example</span></span>  
 <span data-ttu-id="00f95-112">Questo esempio usa il `<remarks>` tag per spiegare cosa `UpdateRecord` fa il metodo.</span><span class="sxs-lookup"><span data-stu-id="00f95-112">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="00f95-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00f95-113">See also</span></span>

- [<span data-ttu-id="00f95-114">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="00f95-114">XML Comment Tags</span></span>](index.md)
