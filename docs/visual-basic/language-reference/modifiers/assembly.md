---
title: Assembly (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
dev_langs:
- VB
helpviewer_keywords:
- Assembly modifier
- Assembly keyword
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b83102c24c80b7ee6ec4c0ffc4a446e26b7811cf
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="assembly-visual-basic"></a><span data-ttu-id="b4b8d-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4b8d-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="b4b8d-103">Specifica che un attributo all'inizio di un file di origine viene applicato all'intero assembly.</span><span class="sxs-lookup"><span data-stu-id="b4b8d-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4b8d-104">Note</span><span class="sxs-lookup"><span data-stu-id="b4b8d-104">Remarks</span></span>  
 <span data-ttu-id="b4b8d-105">Numero di attributi relativi a un singolo elemento di programmazione, ad esempio una classe o una proprietà.</span><span class="sxs-lookup"><span data-stu-id="b4b8d-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="b4b8d-106">Per applicare tale attributo, collegare il blocco di attributi, parentesi angolari (`< >`), direttamente all'istruzione di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="b4b8d-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="b4b8d-107">Se un attributo relativo non solo per il seguente elemento ma non l'intero assembly, inserire il blocco di attributi all'inizio del file di origine e di identificare l'attributo con il `Assembly` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="b4b8d-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="b4b8d-108">Se si applica al modulo in assembly corrente, utilizzare il [modulo](../../../visual-basic/language-reference/modifiers/module-keyword.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="b4b8d-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="b4b8d-109">È inoltre possibile applicare un attributo a un assembly nel file AssemblyInfo. vb, nel qual caso non è necessario utilizzare un blocco di attributi nel file di codice sorgente principale.</span><span class="sxs-lookup"><span data-stu-id="b4b8d-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4b8d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4b8d-110">See Also</span></span>  
 <span data-ttu-id="b4b8d-111">[Modulo \<parola chiave >](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span><span class="sxs-lookup"><span data-stu-id="b4b8d-111">[Module \<keyword>](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span></span>  
<span data-ttu-id="b4b8d-112"> [Panoramica degli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md)</span><span class="sxs-lookup"><span data-stu-id="b4b8d-112"> [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md)</span></span>


