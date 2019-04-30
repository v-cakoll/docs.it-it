---
title: Promozione tipo (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
ms.openlocfilehash: f7ac6bfb944da8bd50e035ba97b2b513176dc661
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973303"
---
# <a name="type-promotion-visual-basic"></a>Promozione tipo (Visual Basic)
Quando si dichiara un elemento di programmazione in un modulo, Visual Basic Alza di livello dell'ambito dello spazio dei nomi che contiene il modulo. Questo è noto come *promozione tipo*.  
  
 L'esempio seguente illustra una struttura di definizione di un modulo e due membri di tale modulo.  
  
 [!code-vb[VbVbalrDeclaredElements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#1)]  
  
 All'interno `projModule`, programmazione gli elementi dichiarati a livello di modulo vengono promosse a `projNamespace`. Nell'esempio precedente, `basicEnum` e `innerClass` alzate di livello, ma `numberSub` non lo è, in quanto non è dichiarato a livello di modulo.  
  
## <a name="effect-of-type-promotion"></a>Effetto della promozione tipo  
 L'effetto della promozione del tipo è che la stringa di qualificazione non è necessario includere il nome del modulo. Nell'esempio seguente effettua due chiamate alla procedura nell'esempio precedente.  
  
 [!code-vb[VbVbalrDeclaredElements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#2)]  
  
 Nell'esempio precedente, la prima chiamata Usa le stringhe di qualificazione completo. Tuttavia, ciò non è necessario a causa di promozione del tipo. La seconda chiamata anche gli accessi i membri del modulo senza includere `projModule` nelle stringhe di qualificazione.  
  
## <a name="defeat-of-type-promotion"></a>Annullamento dell'effetto della promozione del tipo  
 Se lo spazio dei nomi ha già un membro con lo stesso nome di un membro del modulo, la promozione del tipo viene annullato per tale membro. Nell'esempio seguente illustra una struttura di definizione di un modulo all'interno dello stesso spazio dei nomi e un'enumerazione.  
  
 [!code-vb[VbVbalrDeclaredElements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#3)]  
  
 Nell'esempio precedente, Visual Basic non è possibile alzare di livello classe `abc` a `thisNameSpace` perché esiste già un'enumerazione con lo stesso nome a livello di spazio dei nomi. Per accedere `abcSub`, è necessario usare la stringa di qualificazione completo `thisNamespace.thisModule.abc.abcSub`. Classe tuttavia `xyz` comunque viene promosso, ed è possibile accedere `xyzSub` con la stringa di qualificazione più breve `thisNamespace.xyz.xyzSub`.  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>Annullamento dell'effetto della promozione del tipo per i tipi parziali  
 Se una classe o struttura all'interno di un modulo Usa la [parziale](../../../../visual-basic/language-reference/modifiers/partial.md) (parola chiave), la promozione del tipo viene automaticamente annullato per quella classe o struttura, se lo spazio dei nomi è un membro con lo stesso nome. Gli altri elementi nel modulo sono ancora idonee per la promozione del tipo.  
  
 **Conseguenze.** Annullamento dell'effetto della promozione del tipo di una definizione parziale può causare risultati imprevisti e persino errori del compilatore. L'esempio seguente illustra alcune definizioni parziali di una classe, uno dei quali è all'interno di un modulo.  
  
 [!code-vb[VbVbalrDeclaredElements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#4)]  
  
 Nell'esempio precedente, lo sviluppatore potrebbe prevedere il compilatore per unire le due definizioni parziali di `sampleClass`. Tuttavia, il compilatore non considera la promozione per la definizione parziale all'interno di `sampleModule`. Di conseguenza, tenta di compilare due classi separate e distinte, entrambi denominati `sampleClass` ma con percorsi di qualificazione differenti.  
  
 Il compilatore unisce le definizioni parziali solo se i relativi percorsi completi sono identici.  
  
## <a name="recommendations"></a>Suggerimenti  
 I consigli seguenti rappresentano una buona norma di programmazione.  
  
- **Nomi univoci.** Quando si dispone di controllo completo sulla denominazione di elementi di programmazione, è sempre una buona idea utilizzare nomi univoci ovunque. I nomi identici richiedono una qualificazione aggiuntiva e possono rendere difficile leggere il codice. Possono tuttavia portare a piccoli errori e risultati imprevisti.  
  
- **Nome completo.** Quando si lavora con i moduli e gli altri elementi dello stesso spazio dei nomi, l'approccio più sicuro consiste nell'utilizzare sempre il nome completo per tutti gli elementi di programmazione. Se la promozione del tipo viene annullato per un membro del modulo e non qualificare completamente tale membro, è possibile accedere accidentalmente un elemento di programmazione diversi.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Module](../../../../visual-basic/language-reference/statements/module-statement.md)
- [Istruzione Namespace](../../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)
- [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Procedura: Controllare l'ambito di una variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
