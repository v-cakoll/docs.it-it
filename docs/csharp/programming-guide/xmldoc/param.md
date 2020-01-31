---
title: <param> - C# Guida alla programmazione
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: d16070a82531519dd276b2ea999623017769d716
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789764"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="8d846-102">> parametri \<(C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="8d846-102">\<param> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="8d846-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8d846-103">Syntax</span></span>

```xml
<param name="name">description</param>
```

## <a name="parameters"></a><span data-ttu-id="8d846-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="8d846-104">Parameters</span></span>

- `name`

  <span data-ttu-id="8d846-105">Nome di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="8d846-105">The name of a method parameter.</span></span> <span data-ttu-id="8d846-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="8d846-106">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="8d846-107">Descrizione del parametro.</span><span class="sxs-lookup"><span data-stu-id="8d846-107">A description for the parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="8d846-108">Note</span><span class="sxs-lookup"><span data-stu-id="8d846-108">Remarks</span></span>

<span data-ttu-id="8d846-109">Il tag \<param> viene usato nel commento di una dichiarazione di metodo per descrivere uno dei parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="8d846-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="8d846-110">Per documentare più parametri, usare più tag \<param>.</span><span class="sxs-lookup"><span data-stu-id="8d846-110">To document multiple parameters, use multiple \<param> tags.</span></span>

<span data-ttu-id="8d846-111">Il testo del tag \<param> verrà visualizzato in IntelliSense, nella finestra Visualizzatore oggetti e nel report Web sui commenti del codice.</span><span class="sxs-lookup"><span data-stu-id="8d846-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>

<span data-ttu-id="8d846-112">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="8d846-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="8d846-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="8d846-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a><span data-ttu-id="8d846-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d846-114">See also</span></span>

- [<span data-ttu-id="8d846-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="8d846-115">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="8d846-116">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="8d846-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
