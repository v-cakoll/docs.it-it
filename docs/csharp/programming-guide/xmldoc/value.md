---
title: '&lt;value&gt; (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <value>
dev_langs:
- CSharp
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 71c8d5ab2e99291f05ef362960b0eeac969e9de1
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="ltvaluegt-c-programming-guide"></a><span data-ttu-id="0a1c3-102">&lt;value&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="0a1c3-102">&lt;value&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="0a1c3-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a1c3-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a1c3-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="0a1c3-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="0a1c3-105">Descrizione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="0a1c3-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a1c3-106">Note</span><span class="sxs-lookup"><span data-stu-id="0a1c3-106">Remarks</span></span>  
 <span data-ttu-id="0a1c3-107">Il tag \<value> consente di descrivere il valore che rappresenta una proprietà.</span><span class="sxs-lookup"><span data-stu-id="0a1c3-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="0a1c3-108">Si noti che quando si aggiunge una proprietà tramite la procedura guidata per il codice nell'ambiente di sviluppo di Visual Studio .NET, verrà aggiunto un tag [ \<summary>](../../../csharp/programming-guide/xmldoc/summary.md) per la nuova proprietà.</span><span class="sxs-lookup"><span data-stu-id="0a1c3-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="0a1c3-109">È quindi necessario aggiungere manualmente un tag \<value> per descrivere il valore rappresentato dalla proprietà.</span><span class="sxs-lookup"><span data-stu-id="0a1c3-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="0a1c3-110">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="0a1c3-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a1c3-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="0a1c3-111">Example</span></span>  
 <span data-ttu-id="0a1c3-112">[!code-cs[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0a1c3-112">[!code-cs[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a1c3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a1c3-113">See Also</span></span>  
 <span data-ttu-id="0a1c3-114">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0a1c3-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="0a1c3-115">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="0a1c3-115">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

