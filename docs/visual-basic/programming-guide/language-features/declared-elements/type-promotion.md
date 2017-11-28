---
title: Promozione tipo (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f3a55c023afe7afe96f862f0b3cbbdb03a15b902
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="type-promotion-visual-basic"></a>Promozione tipo (Visual Basic)
Quando si dichiara un elemento di programmazione in un modulo, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] promuove l'ambito allo spazio dei nomi che contiene il modulo. Questo è noto come *promozione del tipo*.  
  
 Nell'esempio seguente mostra una struttura di definizione di un modulo e due membri del modulo.  
  
 [!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 All'interno di `projModule`, programmazione gli elementi dichiarati a livello di modulo vengono promossi alla `projNamespace`. Nell'esempio precedente, `basicEnum` e `innerClass` vengono alzate di livello, ma `numberSub` non lo è, poiché non è stato dichiarato a livello di modulo.  
  
## <a name="effect-of-type-promotion"></a>Effetto della promozione del tipo  
 L'effetto della promozione del tipo è che la stringa di qualificazione non è necessario includere il nome del modulo. Nell'esempio seguente effettua le due chiamate alla procedura nell'esempio precedente.  
  
 [!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 Nell'esempio precedente, la prima chiamata utilizza stringhe di qualificazione completo. Tuttavia, questo non è necessario a causa di promozione del tipo. La seconda chiamata anche gli accessi ai membri del modulo senza includere `projModule` nelle stringhe di qualificazione.  
  
## <a name="defeat-of-type-promotion"></a>Annullamento dell'effetto della promozione del tipo  
 Se lo spazio dei nomi contiene già un membro con lo stesso nome di un membro di modulo, la promozione del tipo viene annullato per tale membro. Nell'esempio seguente viene illustrata una definizione di base di un'enumerazione e un modulo entro lo stesso spazio dei nomi.  
  
 [!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 Nell'esempio precedente, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] non è possibile promuovere la classe `abc` a `thisNameSpace` perché esiste già un'enumerazione con lo stesso nome a livello di spazio dei nomi. Per accedere a `abcSub`, è necessario utilizzare la stringa di qualificazione completo `thisNamespace.thisModule.abc.abcSub`. Tuttavia, classe `xyz` ancora viene promosso, ed è possibile accedere `xyzSub` più breve stringa di qualificazione `thisNamespace.xyz.xyzSub`.  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>Annullamento dell'effetto della promozione del tipo per i tipi parziali  
 Se una classe o struttura all'interno di un modulo viene utilizzato il [parziale](../../../../visual-basic/language-reference/modifiers/partial.md) (parola chiave), la promozione del tipo viene automaticamente annullato per quella classe o struttura, se lo spazio dei nomi è un membro con lo stesso nome. Gli altri elementi nel modulo sono comunque idonei per la promozione del tipo.  
  
 **Conseguenze.** Annullamento dell'effetto della promozione del tipo di una definizione parziale può causare risultati imprevisti e persino errori del compilatore. L'esempio seguente mostra alcune definizioni parziali di una classe, uno dei quali è all'interno di un modulo.  
  
 [!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 Nell'esempio precedente, lo sviluppatore può aspettarsi che il compilatore per unire le due definizioni parziali di `sampleClass`. Tuttavia, il compilatore non considera l'innalzamento di livello per la definizione parziale all'interno di `sampleModule`. Di conseguenza, il tentativo di compilare due classi separate e distinte, entrambi denominati `sampleClass` ma con percorsi di qualificazione differenti.  
  
 Il compilatore unisce le definizioni parziali solo se i relativi percorsi completi sono identici.  
  
## <a name="recommendations"></a>Suggerimenti  
 Le indicazioni seguenti rappresentano una buona norma di programmazione.  
  
-   **Nomi univoci.** Quando si dispone di un controllo completo sulla denominazione degli elementi di programmazione, è sempre consigliabile utilizzare nomi univoci ovunque. I nomi identici richiedono una qualificazione aggiuntiva e possono rendere difficile leggere il codice. Essi possono causare errori difficili da rilevare e risultati imprevisti.  
  
-   **Nome completo.** Quando si lavora con i moduli e altri elementi dello stesso spazio dei nomi, l'approccio più sicuro è utilizzare sempre il nome completo per tutti gli elementi di programmazione. Se la promozione del tipo viene annullato per il membro di un modulo e non qualificare completamente tale membro, è possibile accedere inavvertitamente un elemento di programmazione diverso.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Module](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [Istruzione Namespace](../../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [Ambito in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Procedura: controllare l'ambito di una variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
