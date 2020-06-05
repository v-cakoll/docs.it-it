---
title: Modulo<keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: 0cb009c22dada7b92956e113d33505923a92f2b3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362424"
---
# <a name="module-keyword-visual-basic"></a><span data-ttu-id="ea9e9-102">Modulo \<keyword> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea9e9-102">Module \<keyword> (Visual Basic)</span></span>
<span data-ttu-id="ea9e9-103">Specifica che un attributo all'inizio di un file di origine viene applicato al modulo di assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="ea9e9-103">Specifies that an attribute at the beginning of a source file applies to the current assembly module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea9e9-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="ea9e9-104">Remarks</span></span>  
 <span data-ttu-id="ea9e9-105">Molti attributi riguardano un singolo elemento di programmazione, ad esempio una classe o una proprietà.</span><span class="sxs-lookup"><span data-stu-id="ea9e9-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="ea9e9-106">Applicare tale attributo alleghindo il blocco di attributi, racchiuso tra parentesi acute ( `< >` ), direttamente all'istruzione di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="ea9e9-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="ea9e9-107">Se un attributo riguarda non solo l'elemento seguente ma al modulo di assembly corrente, il blocco di attributi viene inserito all'inizio del file di origine e l'attributo viene identificato con la `Module` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="ea9e9-107">If an attribute pertains not only to the following element but to the current assembly module, you place the attribute block at the beginning of the source file and identify the attribute with the `Module` keyword.</span></span> <span data-ttu-id="ea9e9-108">Se si applica all'intero assembly, usare la parola chiave [assembly](assembly.md) .</span><span class="sxs-lookup"><span data-stu-id="ea9e9-108">If it applies to the entire assembly, you use the [Assembly](assembly.md) keyword.</span></span>  
  
 <span data-ttu-id="ea9e9-109">Il `Module` modificatore non è uguale all' [istruzione Module](../statements/module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ea9e9-109">The `Module` modifier is not the same as the [Module Statement](../statements/module-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea9e9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea9e9-110">See also</span></span>

- [<span data-ttu-id="ea9e9-111">Assembly</span><span class="sxs-lookup"><span data-stu-id="ea9e9-111">Assembly</span></span>](assembly.md)
- [<span data-ttu-id="ea9e9-112">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="ea9e9-112">Module Statement</span></span>](../statements/module-statement.md)
- [<span data-ttu-id="ea9e9-113">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="ea9e9-113">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
