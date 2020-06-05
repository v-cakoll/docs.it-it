---
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 3a2452ec60a2182adfee365777d9824001ff006a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400124"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="adfe5-101">\<exception> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="adfe5-101">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="adfe5-102">Specifica le eccezioni che possono essere generate.</span><span class="sxs-lookup"><span data-stu-id="adfe5-102">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adfe5-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="adfe5-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="adfe5-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="adfe5-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="adfe5-105">Riferimento ad un'eccezione disponibile dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="adfe5-105">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="adfe5-106">Il compilatore controlla che l'eccezione specificata esista e converte `member` nel nome canonico dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="adfe5-106">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="adfe5-107">`member` deve essere racchiuso tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="adfe5-107">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="adfe5-108">Una descrizione.</span><span class="sxs-lookup"><span data-stu-id="adfe5-108">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adfe5-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="adfe5-109">Remarks</span></span>  
 <span data-ttu-id="adfe5-110">Usare il `<exception>` tag per specificare le eccezioni che possono essere generate.</span><span class="sxs-lookup"><span data-stu-id="adfe5-110">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="adfe5-111">Questo tag viene applicato a una definizione di metodo.</span><span class="sxs-lookup"><span data-stu-id="adfe5-111">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="adfe5-112">Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="adfe5-112">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adfe5-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="adfe5-113">Example</span></span>  
 <span data-ttu-id="adfe5-114">Questo esempio usa il `<exception>` tag per descrivere un'eccezione che la `IntDivide` funzione può generare.</span><span class="sxs-lookup"><span data-stu-id="adfe5-114">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="adfe5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="adfe5-115">See also</span></span>

- [<span data-ttu-id="adfe5-116">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="adfe5-116">XML Comment Tags</span></span>](index.md)
