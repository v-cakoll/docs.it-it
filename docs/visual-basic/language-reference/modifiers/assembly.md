---
title: Assembly (Visual Basic)
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
ms.openlocfilehash: 7ee6cddefd5955ee76510ffeb23335f05460657b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595290"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="837a3-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="837a3-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="837a3-103">Specifica che un attributo all'inizio di un file di origine viene applicato all'intero assembly.</span><span class="sxs-lookup"><span data-stu-id="837a3-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="837a3-104">Note</span><span class="sxs-lookup"><span data-stu-id="837a3-104">Remarks</span></span>  
 <span data-ttu-id="837a3-105">Numero di attributi relativi a un singolo elemento di programmazione, ad esempio una classe o proprietà.</span><span class="sxs-lookup"><span data-stu-id="837a3-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="837a3-106">Per applicare tale attributo, collegare il blocco di attributi tra parentesi angolari (`< >`), direttamente all'istruzione di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="837a3-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="837a3-107">Se un attributo relativo non solo per il seguente elemento ma non all'intero assembly, inserire il blocco di attributi all'inizio del file di origine e di identificare l'attributo con il `Assembly` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="837a3-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="837a3-108">Se si applica al modulo in assembly corrente, utilizzare il [modulo](../../../visual-basic/language-reference/modifiers/module-keyword.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="837a3-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="837a3-109">È inoltre possibile applicare un attributo a un assembly nel file AssemblyInfo. vb, nel qual caso non è necessario utilizzare un blocco di attributi nel file di codice sorgente principale.</span><span class="sxs-lookup"><span data-stu-id="837a3-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="837a3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="837a3-110">See Also</span></span>  
 [<span data-ttu-id="837a3-111">Modulo \<parola chiave></span><span class="sxs-lookup"><span data-stu-id="837a3-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [<span data-ttu-id="837a3-112">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="837a3-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

