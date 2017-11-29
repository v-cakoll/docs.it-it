---
title: '&lt;valore&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a72c6330596e59d26fbae9d13f6b9c8b1987e519
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltvaluegt-visual-basic"></a><span data-ttu-id="3d085-102">&lt;valore&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d085-102">&lt;value&gt; (Visual Basic)</span></span>
<span data-ttu-id="3d085-103">Specifica la descrizione di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="3d085-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d085-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d085-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d085-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d085-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="3d085-106">Descrizione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="3d085-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d085-107">Note</span><span class="sxs-lookup"><span data-stu-id="3d085-107">Remarks</span></span>  
 <span data-ttu-id="3d085-108">Utilizzare il `<value>` tag per descrivere una proprietà.</span><span class="sxs-lookup"><span data-stu-id="3d085-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="3d085-109">Si noti che quando si aggiunge una proprietà utilizzando la procedura guidata codice nell'ambiente di sviluppo di Visual Studio, verrà aggiunto un [ \<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md) tag per la nuova proprietà.</span><span class="sxs-lookup"><span data-stu-id="3d085-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="3d085-110">È quindi necessario aggiungere manualmente un `<value>` tag per descrivere il valore che rappresenta la proprietà.</span><span class="sxs-lookup"><span data-stu-id="3d085-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="3d085-111">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="3d085-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d085-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="3d085-112">Example</span></span>  
 <span data-ttu-id="3d085-113">Questo esempio viene utilizzato il `<value>` tag per descrivere il valore di `Counter` contiene proprietà.</span><span class="sxs-lookup"><span data-stu-id="3d085-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3d085-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d085-114">See Also</span></span>  
 [<span data-ttu-id="3d085-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="3d085-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
