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
ms.openlocfilehash: 1385919a1205a60104125fff1bdd24f409a091df
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351641"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="83979-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83979-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="83979-103">Specifica che un attributo all'inizio di un file di origine viene applicato all'intero assembly.</span><span class="sxs-lookup"><span data-stu-id="83979-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83979-104">Note</span><span class="sxs-lookup"><span data-stu-id="83979-104">Remarks</span></span>  
 <span data-ttu-id="83979-105">Molti attributi riguardano un singolo elemento di programmazione, ad esempio una classe o una proprietà.</span><span class="sxs-lookup"><span data-stu-id="83979-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="83979-106">Applicare tale attributo alleghindo il blocco di attributi, racchiuso tra parentesi angolari (`< >`), direttamente all'istruzione di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="83979-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="83979-107">Se un attributo riguarda non solo l'elemento seguente ma l'intero assembly, il blocco di attributi viene inserito all'inizio del file di origine e l'attributo viene identificato con la parola chiave `Assembly`.</span><span class="sxs-lookup"><span data-stu-id="83979-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="83979-108">Se si applica al modulo di assembly corrente, usare la parola chiave [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) .</span><span class="sxs-lookup"><span data-stu-id="83979-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="83979-109">È anche possibile applicare un attributo a un assembly nel file AssemblyInfo. vb, nel qual caso non è necessario usare un blocco di attributi nel file del codice sorgente principale.</span><span class="sxs-lookup"><span data-stu-id="83979-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83979-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83979-110">See also</span></span>

- [<span data-ttu-id="83979-111">Modulo \<parola chiave></span><span class="sxs-lookup"><span data-stu-id="83979-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [<span data-ttu-id="83979-112">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="83979-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
