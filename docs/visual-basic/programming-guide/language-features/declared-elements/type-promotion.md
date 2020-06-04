---
title: Promozione tipo
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
ms.openlocfilehash: 1e284b99a36cdf0f62aee2c45fd9f3bf544d1d81
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410708"
---
# <a name="type-promotion-visual-basic"></a>Promozione tipo (Visual Basic)
Quando si dichiara un elemento di programmazione in un modulo, Visual Basic promuove l'ambito dello spazio dei nomi che contiene il modulo. Questa operazione è nota come *innalzamento di tipo*.  
  
 Nell'esempio seguente viene illustrata una definizione di scheletro di un modulo e di due membri del modulo.  
  
 [!code-vb[VbVbalrDeclaredElements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#1)]  
  
 In `projModule` gli elementi di programmazione dichiarati a livello di modulo vengono promossi a `projNamespace` . Nell'esempio precedente, `basicEnum` e `innerClass` sono innalzati di livello, ma `numberSub` non lo sono, perché non è dichiarato a livello di modulo.  
  
## <a name="effect-of-type-promotion"></a>Effetto della promozione del tipo  
 L'effetto della promozione del tipo è che una stringa di qualificazione non deve includere il nome del modulo. Nell'esempio seguente vengono effettuate due chiamate alla procedura nell'esempio precedente.  
  
 [!code-vb[VbVbalrDeclaredElements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#2)]  
  
 Nell'esempio precedente, la prima chiamata usa le stringhe di qualificazione complete. Tuttavia, ciò non è necessario a causa della promozione del tipo. La seconda chiamata accede anche ai membri del modulo senza includere `projModule` nelle stringhe di qualificazione.  
  
## <a name="defeat-of-type-promotion"></a>Sconfitta della promozione del tipo  
 Se lo spazio dei nomi ha già un membro con lo stesso nome di un membro del modulo, la promozione del tipo viene sconfitta per quel membro del modulo. Nell'esempio seguente viene illustrata una definizione di scheletro di un'enumerazione e di un modulo all'interno dello stesso spazio dei nomi.  
  
 [!code-vb[VbVbalrDeclaredElements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#3)]  
  
 Nell'esempio precedente, Visual Basic non è in grado `abc` di innalzare di livello la classe a `thisNameSpace` perché esiste già un'enumerazione con lo stesso nome a livello di spazio dei nomi. Per accedere a `abcSub` , è necessario usare la stringa di qualificazione completa `thisNamespace.thisModule.abc.abcSub` . Tuttavia, `xyz` la classe viene comunque innalzata di livello ed è possibile accedere `xyzSub` con la stringa di qualificazione più breve `thisNamespace.xyz.xyzSub` .  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>Sconfitta della promozione del tipo per i tipi parziali  
 Se una classe o una struttura all'interno di un modulo usa la parola chiave [partial](../../../language-reference/modifiers/partial.md) , l'innalzamento di livello viene automaticamente sconfitto per quella classe o struttura, indipendentemente dal fatto che lo spazio dei nomi abbia un membro con lo stesso nome. Gli altri elementi del modulo sono ancora idonei per la promozione del tipo.  
  
 **Conseguenze.** La sconfitta della promozione del tipo di una definizione parziale può causare risultati imprevisti e persino errori del compilatore. Nell'esempio seguente vengono illustrate le definizioni parziali di una classe, una delle quali si trova all'interno di un modulo.  
  
 [!code-vb[VbVbalrDeclaredElements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#4)]  
  
 Nell'esempio precedente, lo sviluppatore potrebbe prevedere che il compilatore possa unire le due definizioni parziali di `sampleClass` . Tuttavia, il compilatore non considera la promozione per la definizione parziale all'interno di `sampleModule` . Di conseguenza, tenta di compilare due classi separate e distinte, entrambe denominate `sampleClass` ma con percorsi di qualificazione diversi.  
  
 Il compilatore unisce le definizioni parziali solo se i relativi percorsi completi sono identici.  
  
## <a name="recommendations"></a>Consigli  
 Le indicazioni seguenti rappresentano una procedura di programmazione efficace.  
  
- **Nomi univoci.** Quando si ha il controllo completo sulla denominazione degli elementi di programmazione, è sempre consigliabile usare nomi univoci in tutto il mondo. I nomi identici richiedono una qualificazione aggiuntiva e possono rendere il codice più difficile da leggere. Possono anche causare errori sottili e risultati imprevisti.  
  
- **Qualificazione completa.** Quando si lavora con i moduli e altri elementi nello stesso spazio dei nomi, l'approccio più sicuro consiste nel usare sempre la qualifica completa per tutti gli elementi di programmazione. Se la promozione del tipo viene sconfitta per un membro del modulo e non si qualifica completamente tale membro, è possibile accedere inavvertitamente a un altro elemento di programmazione.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Module](../../../language-reference/statements/module-statement.md)
- [Istruzione Namespace](../../../language-reference/statements/namespace-statement.md)
- [Partial](../../../language-reference/modifiers/partial.md)
- [Ambito in Visual Basic](scope.md)
- [Procedura: controllare l'ambito di una variabile](how-to-control-the-scope-of-a-variable.md)
- [References to Declared Elements](references-to-declared-elements.md)
