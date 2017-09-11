---
title: '&lt;permission&gt; (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- permission
- <permission>
dev_langs:
- CSharp
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
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
ms.openlocfilehash: 4b8f109d7e01f6e630f09939161b6a20c3a13f73
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="ltpermissiongt-c-programming-guide"></a><span data-ttu-id="e97b1-102">&lt;permission&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e97b1-102">&lt;permission&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="e97b1-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e97b1-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e97b1-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="e97b1-104">Parameters</span></span>  
 <span data-ttu-id="e97b1-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="e97b1-105">cref = " `member`"</span></span>  
 <span data-ttu-id="e97b1-106">Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="e97b1-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="e97b1-107">Il compilatore verifica l'esistenza dell'elemento di codice specificato e converte `member` nel nome canonico dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="e97b1-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="e97b1-108">*member* deve essere racchiuso tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="e97b1-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="e97b1-109">Per informazioni su come creare un riferimento cref a un tipo generico, vedere [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="e97b1-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="e97b1-110">Descrizione dell'accesso al membro.</span><span class="sxs-lookup"><span data-stu-id="e97b1-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e97b1-111">Note</span><span class="sxs-lookup"><span data-stu-id="e97b1-111">Remarks</span></span>  
 <span data-ttu-id="e97b1-112">Il tag \<permission> consente di documentare l'accesso a un membro.</span><span class="sxs-lookup"><span data-stu-id="e97b1-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="e97b1-113">La classe <xref:System.Security.PermissionSet> consente di specificare l'accesso a un membro.</span><span class="sxs-lookup"><span data-stu-id="e97b1-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="e97b1-114">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="e97b1-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e97b1-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="e97b1-115">Example</span></span>  
 <span data-ttu-id="e97b1-116">[!code-cs[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e97b1-116">[!code-cs[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e97b1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e97b1-117">See Also</span></span>  
 <span data-ttu-id="e97b1-118">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e97b1-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="e97b1-119">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="e97b1-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

