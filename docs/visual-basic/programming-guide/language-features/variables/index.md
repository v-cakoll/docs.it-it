---
title: Variabili in Visual Basic | Microsoft Docs
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
caps.latest.revision: 27
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 9a19838abed2d947e8e7ebf96fa4603feb208012
ms.contentlocale: it-it
ms.lasthandoff: 05/26/2017

---
<a id="variables-in-visual-basic" class="xliff"></a>

# Variabili in Visual Basic
Quando si eseguono calcoli con [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] è spesso necessario archiviare i valori. È possibile ad esempio che si vogliano calcolare valori diversi, confrontarli ed eseguire operazioni su di essi a seconda del risultato del confronto. Per poter confrontare i valori è necessario archiviarli.  
  
<a id="usage" class="xliff"></a>

## Utilizzo  
 Come la maggior parte dei linguaggi di programmazione, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] usa le variabili per archiviare i valori. Ogni *variabile* ha un nome, ovvero la parola usata per fare riferimento al valore contenuto nella variabile. Ogni variabile ha anche un tipo di dati che determina il genere di dati che la variabile può archiviare. Una variabile può rappresentare una matrice se deve archiviare un insieme indicizzato di elementi di dati strettamente correlati.  
  
 L'inferenza del tipo di variabile locale consente di dichiarare le variabili senza specificare esplicitamente un tipo di dati. In questo caso, il compilatore deduce il tipo della variabile in base al tipo dell'espressione di inizializzazione. Per altre informazioni, vedere [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) (Inferenza del tipo di variabile locale) e [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) (Istruzione Option Infer).  
  
<a id="assigning-values" class="xliff"></a>

## Assegnazione di valori  
 Le istruzioni di assegnazione consentono di eseguire i calcoli e assegnare il risultato a una variabile, come illustra l'esempio seguente.  
  
 [!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]  
  
> [!NOTE]
>  Il segno di uguale (`=`) in questo esempio è un operatore di assegnazione, non un operatore di uguaglianza. Il valore viene assegnato alla variabile `applesSold`.  
  
 Per altre informazioni, vedere [Procedura: Spostare i dati all'interno e all'esterno di una variabile](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).  
  
<a id="variables-and-properties" class="xliff"></a>

## Variabili e proprietà  
 Analogamente a una variabile, una *proprietà* rappresenta un valore al quale è possibile accedere. Le proprietà sono tuttavia più complesse delle variabili. Le proprietà usano blocchi di codice che controllano come impostare e recuperare il valore della proprietà. Per altre informazioni, vedere [Differenze tra proprietà e variabili in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).  
  
<a id="see-also" class="xliff"></a>

## Vedere anche  
 [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Risoluzione dei problemi relativi alle variabili](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)   
 [Procedura: Spostare i dati all'interno e all'esterno di una variabile](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)   
 [Differenze tra proprietà e variabili in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
