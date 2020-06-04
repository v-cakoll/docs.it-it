---
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 893ed299b46bd6255ca0e87d008ac53265698614
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411499"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="663fc-101">\<summary> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="663fc-101">\<summary> (Visual Basic)</span></span>
<span data-ttu-id="663fc-102">Specifica il riepilogo del membro.</span><span class="sxs-lookup"><span data-stu-id="663fc-102">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="663fc-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="663fc-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="663fc-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="663fc-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="663fc-105">Un riepilogo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="663fc-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="663fc-106">Commenti</span><span class="sxs-lookup"><span data-stu-id="663fc-106">Remarks</span></span>  
 <span data-ttu-id="663fc-107">Usare il `<summary>` tag per descrivere un tipo o un membro del tipo.</span><span class="sxs-lookup"><span data-stu-id="663fc-107">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="663fc-108">Utilizzare [\<remarks>](remarks.md) per aggiungere informazioni aggiuntive a una descrizione del tipo.</span><span class="sxs-lookup"><span data-stu-id="663fc-108">Use [\<remarks>](remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="663fc-109">Il testo per il `<summary>` tag è l'unica fonte di informazioni sul tipo in IntelliSense e viene visualizzato anche nell'Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="663fc-109">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="663fc-110">Per informazioni sulla Visualizzatore oggetti, vedere [visualizzazione della struttura del codice](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="663fc-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="663fc-111">Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="663fc-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="663fc-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="663fc-112">Example</span></span>  
 <span data-ttu-id="663fc-113">Questo esempio usa il `<summary>` tag per descrivere il `ResetCounter` metodo e la `Counter` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="663fc-113">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="663fc-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="663fc-114">See also</span></span>

- [<span data-ttu-id="663fc-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="663fc-115">XML Comment Tags</span></span>](index.md)
