---
title: <param> -Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 396ed716c246091a674268020261069f36dd2be8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287324"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="c1080-102">\<param>(Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="c1080-102">\<param> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="c1080-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1080-103">Syntax</span></span>

```xml
<param name="name">description</param>
```

## <a name="parameters"></a><span data-ttu-id="c1080-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="c1080-104">Parameters</span></span>

- `name`

  <span data-ttu-id="c1080-105">Nome di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="c1080-105">The name of a method parameter.</span></span> <span data-ttu-id="c1080-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="c1080-106">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="c1080-107">Descrizione del parametro.</span><span class="sxs-lookup"><span data-stu-id="c1080-107">A description for the parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1080-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c1080-108">Remarks</span></span>

<span data-ttu-id="c1080-109">Il `<param>` tag deve essere usato nel commento per una dichiarazione di metodo per descrivere uno dei parametri per il metodo.</span><span class="sxs-lookup"><span data-stu-id="c1080-109">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="c1080-110">Per documentare più parametri, usare più `<param>` tag.</span><span class="sxs-lookup"><span data-stu-id="c1080-110">To document multiple parameters, use multiple `<param>` tags.</span></span>

<span data-ttu-id="c1080-111">Il testo per il `<param>` tag viene visualizzato in IntelliSense, il Visualizzatore oggetti e il report Web di commenti sul codice.</span><span class="sxs-lookup"><span data-stu-id="c1080-111">The text for the `<param>` tag is displayed in IntelliSense, the Object Browser, and the Code Comment Web Report.</span></span>

<span data-ttu-id="c1080-112">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="c1080-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="c1080-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="c1080-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a><span data-ttu-id="c1080-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1080-114">See also</span></span>

- [<span data-ttu-id="c1080-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c1080-115">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="c1080-116">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="c1080-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
