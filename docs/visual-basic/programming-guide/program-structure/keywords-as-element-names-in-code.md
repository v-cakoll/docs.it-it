---
title: Parole chiave come nomi di elementi nel codice
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: a98f0b027700717b414d58e1284ddec655eb25f7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403226"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>Parole chiave come nomi di elementi nel codice (Visual Basic)
Qualsiasi elemento del programma, ad esempio una variabile, una classe o un membro, può avere lo stesso nome di una parola chiave con restrizioni. Ad esempio, è possibile creare una variabile denominata `Loop` . Tuttavia, per fare riferimento alla relativa versione, che ha lo stesso nome della parola chiave Restricted, `Loop` è necessario precederla con una stringa di qualificazione completa o racchiuderla tra parentesi quadre ( `[ ]` ), come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 Se non si esegue una di queste operazioni, Visual Basic presuppone l'uso della `Loop` parola chiave intrinseca e genera un errore, come nell'esempio seguente:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 È possibile utilizzare le parentesi quadre per fare riferimento a form e controlli e quando si dichiara una variabile o si definisce una routine con lo stesso nome di una parola chiave con restrizioni. Può essere facile dimenticare di qualificare i nomi o includere le parentesi quadre e quindi introdurre errori nel codice e renderlo più difficile da leggere. Per questo motivo, è consigliabile non usare parole chiave con restrizioni come nomi degli elementi del programma. Tuttavia, se una versione futura di Visual Basic definisce una parola chiave nuova che è in conflitto con un modulo o un nome di controllo esistente, è possibile utilizzare questa tecnica quando si aggiorna il codice per utilizzare la nuova versione.  
  
> [!NOTE]
> Il programma può inoltre includere i nomi degli elementi forniti da altri assembly a cui si fa riferimento. Se questi nomi sono in conflitto con parole chiave con restrizioni, l'inserimento di parentesi quadre attorno ad essi causa la Visual Basic di interpretarli come elementi definiti.  
  
## <a name="see-also"></a>Vedere anche

- [Convenzioni di denominazione di Visual Basic](naming-conventions.md)
- [Struttura del programma e convenzioni del codice](program-structure-and-code-conventions.md)
- [Parole chiave](../../language-reference/keywords/index.md)
