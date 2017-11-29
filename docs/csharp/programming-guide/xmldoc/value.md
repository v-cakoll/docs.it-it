---
title: '&lt;value&gt; (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9ea900c21c2c0477c626be5eff2403312d9e8609
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltvaluegt-c-programming-guide"></a><span data-ttu-id="d0146-102">&lt;value&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d0146-102">&lt;value&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="d0146-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d0146-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0146-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="d0146-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="d0146-105">Descrizione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d0146-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0146-106">Note</span><span class="sxs-lookup"><span data-stu-id="d0146-106">Remarks</span></span>  
 <span data-ttu-id="d0146-107">Il tag \<value> consente di descrivere il valore che rappresenta una proprietà.</span><span class="sxs-lookup"><span data-stu-id="d0146-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="d0146-108">Si noti che quando si aggiunge una proprietà tramite la procedura guidata per il codice nell'ambiente di sviluppo di Visual Studio .NET, verrà aggiunto un tag [ \<summary>](../../../csharp/programming-guide/xmldoc/summary.md) per la nuova proprietà.</span><span class="sxs-lookup"><span data-stu-id="d0146-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="d0146-109">È quindi necessario aggiungere manualmente un tag \<value> per descrivere il valore rappresentato dalla proprietà.</span><span class="sxs-lookup"><span data-stu-id="d0146-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="d0146-110">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="d0146-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0146-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0146-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d0146-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0146-112">See Also</span></span>  
 [<span data-ttu-id="d0146-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d0146-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d0146-114">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="d0146-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
