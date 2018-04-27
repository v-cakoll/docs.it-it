---
title: Necessario riferimento all'assembly &#39; &lt;assemblyidentity&gt; &#39; contenente il tipo &#39; &lt;typename&gt;&#39;, ma non è stato possibile trovare un riferimento appropriato a causa dell'ambiguità tra i progetti &#39; &lt;projectname1&gt; &#39; e &#39; &lt;projectname2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 69b1184d47e427bd985c3b18135d4a0ac4d91410
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="reference-required-to-assembly-39ltassemblyidentitygt39-containing-type-39lttypenamegt39-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-39ltprojectname1gt39-and-39ltprojectname2gt39"></a>Necessario riferimento all'assembly &#39; &lt;assemblyidentity&gt; &#39; contenente il tipo &#39; &lt;typename&gt;&#39;, ma non è stato possibile trovare un riferimento appropriato a causa dell'ambiguità tra i progetti &#39; &lt;projectname1&gt; &#39; e &#39; &lt;projectname2&gt;&#39;
In un'espressione viene usato un tipo, ad esempio una classe, una struttura, un'interfaccia, un'enumerazione o un delegato, definito all'esterno del progetto. Tuttavia, sono presenti riferimenti di progetto a più assembly che definiscono quel tipo.  
  
 I progetti citati generano assembly con lo stesso nome. Pertanto, il compilatore non può determinare l'assembly da usare per il tipo a cui si accede.  
  
 Per accedere a un tipo definito in un altro assembly, il compilatore Visual Basic deve includere un riferimento a tale assembly. Deve trattarsi di un riferimento unico, non ambiguo, che non generi riferimenti circolari tra i progetti.  
  
 **ID errore:** BC30969  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Determinare quale progetto produce l'assembly migliore per il progetto a cui fare riferimento. Per questa decisione si potrebbero usare criteri quali la facilità di accesso al file e la frequenza di aggiornamenti.  
  
2.  Nelle proprietà del progetto aggiungere un riferimento al file contenente l'assembly che definisce il tipo in uso.  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)  
 [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
   
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)  
 [Risoluzione dei problemi relativi ai riferimenti interrotti](/visualstudio/ide/troubleshooting-broken-references)
