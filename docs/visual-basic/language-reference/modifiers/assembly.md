---
title: Assembly
ms.date: 07/20/2015
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
ms.openlocfilehash: 7d313dee1015362bd0215ed98ab7e898312cfbcd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373160"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="d156e-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d156e-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="d156e-103">Specifica che un attributo all'inizio di un file di origine viene applicato all'intero assembly.</span><span class="sxs-lookup"><span data-stu-id="d156e-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d156e-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="d156e-104">Remarks</span></span>  
 <span data-ttu-id="d156e-105">Molti attributi riguardano un singolo elemento di programmazione, ad esempio una classe o una proprietà.</span><span class="sxs-lookup"><span data-stu-id="d156e-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="d156e-106">Applicare tale attributo alleghindo il blocco di attributi, racchiuso tra parentesi acute ( `< >` ), direttamente all'istruzione di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="d156e-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="d156e-107">Se un attributo riguarda non solo l'elemento seguente ma l'intero assembly, inserire il blocco di attributi all'inizio del file di origine e identificare l'attributo con la `Assembly` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="d156e-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="d156e-108">Se si applica al modulo di assembly corrente, usare la parola chiave [Module](module-keyword.md) .</span><span class="sxs-lookup"><span data-stu-id="d156e-108">If it applies to the current assembly module, you use the [Module](module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="d156e-109">È anche possibile applicare un attributo a un assembly nel file AssemblyInfo. vb, nel qual caso non è necessario usare un blocco di attributi nel file del codice sorgente principale.</span><span class="sxs-lookup"><span data-stu-id="d156e-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d156e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d156e-110">See also</span></span>

- [<span data-ttu-id="d156e-111">Modulo\<keyword></span><span class="sxs-lookup"><span data-stu-id="d156e-111">Module \<keyword></span></span>](module-keyword.md)
- [<span data-ttu-id="d156e-112">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="d156e-112">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
