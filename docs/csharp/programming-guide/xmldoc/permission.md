---
title: <permission> - Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 67e9d398d1bb43d480f8ca56733106e0f0a22731
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75696571"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="810b9-102">\<permission> (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="810b9-102">\<permission> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="810b9-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="810b9-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="810b9-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="810b9-104">Parameters</span></span>  
 <span data-ttu-id="810b9-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="810b9-105">cref = " `member`"</span></span>  
 <span data-ttu-id="810b9-106">Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="810b9-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="810b9-107">Il compilatore verifica l'esistenza dell'elemento di codice specificato e converte `member` nel nome canonico dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="810b9-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="810b9-108">*member* deve essere racchiuso tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="810b9-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="810b9-109">Per informazioni su come creare un riferimento cref a un tipo generico, vedere [\<see>](./see.md).</span><span class="sxs-lookup"><span data-stu-id="810b9-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="810b9-110">Descrizione dell'accesso al membro.</span><span class="sxs-lookup"><span data-stu-id="810b9-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="810b9-111">Note</span><span class="sxs-lookup"><span data-stu-id="810b9-111">Remarks</span></span>  
 <span data-ttu-id="810b9-112">Il tag \<permission> consente di documentare l'accesso a un membro.</span><span class="sxs-lookup"><span data-stu-id="810b9-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="810b9-113">La classe <xref:System.Security.PermissionSet> consente di specificare l'accesso a un membro.</span><span class="sxs-lookup"><span data-stu-id="810b9-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="810b9-114">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="810b9-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="810b9-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="810b9-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="810b9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="810b9-116">See also</span></span>

- [<span data-ttu-id="810b9-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="810b9-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="810b9-118">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="810b9-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
