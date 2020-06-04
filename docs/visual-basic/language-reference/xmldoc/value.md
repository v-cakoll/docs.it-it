---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 24358a1b004f1cefbfeb3fb8451380ed883841df
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411473"
---
# <a name="value-visual-basic"></a><span data-ttu-id="8fa6f-101">\<value> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fa6f-101">\<value> (Visual Basic)</span></span>
<span data-ttu-id="8fa6f-102">Specifica la descrizione di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="8fa6f-102">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fa6f-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8fa6f-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fa6f-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="8fa6f-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="8fa6f-105">Descrizione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="8fa6f-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fa6f-106">Commenti</span><span class="sxs-lookup"><span data-stu-id="8fa6f-106">Remarks</span></span>  
 <span data-ttu-id="8fa6f-107">Usare il `<value>` tag per descrivere una proprietà.</span><span class="sxs-lookup"><span data-stu-id="8fa6f-107">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="8fa6f-108">Si noti che quando si aggiunge una proprietà usando la creazione guidata codice nell'ambiente di sviluppo di Visual Studio, verrà aggiunto un [\<summary>](summary.md) tag per la nuova proprietà.</span><span class="sxs-lookup"><span data-stu-id="8fa6f-108">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](summary.md) tag for the new property.</span></span> <span data-ttu-id="8fa6f-109">È quindi necessario aggiungere manualmente un `<value>` tag per descrivere il valore rappresentato dalla proprietà.</span><span class="sxs-lookup"><span data-stu-id="8fa6f-109">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="8fa6f-110">Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="8fa6f-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fa6f-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="8fa6f-111">Example</span></span>  
 <span data-ttu-id="8fa6f-112">Questo esempio usa il `<value>` tag per descrivere il valore che la `Counter` proprietà possiede.</span><span class="sxs-lookup"><span data-stu-id="8fa6f-112">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8fa6f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fa6f-113">See also</span></span>

- [<span data-ttu-id="8fa6f-114">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="8fa6f-114">XML Comment Tags</span></span>](index.md)
