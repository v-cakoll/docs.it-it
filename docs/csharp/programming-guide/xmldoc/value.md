---
title: <value> - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 4d967d671b3a27698b457c80ff5a8f7031dc6bcb
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587419"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="b577f-102">\<value> (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="b577f-102">\<value> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="b577f-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b577f-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="b577f-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="b577f-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="b577f-105">Descrizione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b577f-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b577f-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b577f-106">Remarks</span></span>  
 <span data-ttu-id="b577f-107">Il tag \<value> consente di descrivere il valore che rappresenta una proprietà.</span><span class="sxs-lookup"><span data-stu-id="b577f-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="b577f-108">Si noti che quando si aggiunge una proprietà tramite la procedura guidata per il codice nell'ambiente di sviluppo di Visual Studio .NET, verrà aggiunto un tag [ \<summary>](./summary.md) per la nuova proprietà.</span><span class="sxs-lookup"><span data-stu-id="b577f-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="b577f-109">È quindi necessario aggiungere manualmente un tag \<value> per descrivere il valore rappresentato dalla proprietà.</span><span class="sxs-lookup"><span data-stu-id="b577f-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="b577f-110">Compilare con [/doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="b577f-110">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b577f-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="b577f-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]  
  
## <a name="see-also"></a><span data-ttu-id="b577f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b577f-112">See also</span></span>

- [<span data-ttu-id="b577f-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b577f-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b577f-114">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="b577f-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
