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
ms.openlocfilehash: 819fa9cf1bd25e9426fb1e75925a269fcf7a71cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801987"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="d2aab-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2aab-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="d2aab-103">Specifica che un attributo all'inizio di un file di origine si applica all'intero assembly.</span><span class="sxs-lookup"><span data-stu-id="d2aab-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2aab-104">Note</span><span class="sxs-lookup"><span data-stu-id="d2aab-104">Remarks</span></span>  
 <span data-ttu-id="d2aab-105">Numero di attributi si riferiscono a un singolo elemento di programmazione, ad esempio una classe o proprietà.</span><span class="sxs-lookup"><span data-stu-id="d2aab-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="d2aab-106">Per applicare tale attributo, collegare il blocco di attributi, parentesi angolari (`< >`), direttamente nell'istruzione di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="d2aab-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="d2aab-107">Se un attributo relativo non solo per l'elemento seguente ma all'intero assembly, inserire il blocco di attributi all'inizio del file di origine e di identificare l'attributo con il `Assembly` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="d2aab-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="d2aab-108">Se si applica al modulo dell'assembly corrente, usare il [modulo](../../../visual-basic/language-reference/modifiers/module-keyword.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="d2aab-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="d2aab-109">È anche possibile applicare un attributo a un assembly nel file AssemblyInfo. vb, nel qual caso non è necessario usare un blocco di attributi nel file di codice sorgente principale.</span><span class="sxs-lookup"><span data-stu-id="d2aab-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2aab-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2aab-110">See also</span></span>

- [<span data-ttu-id="d2aab-111">Modulo \<parola chiave></span><span class="sxs-lookup"><span data-stu-id="d2aab-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [<span data-ttu-id="d2aab-112">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="d2aab-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
