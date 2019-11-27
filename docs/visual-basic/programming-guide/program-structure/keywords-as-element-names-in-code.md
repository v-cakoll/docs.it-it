---
title: Parole chiave come nomi di elementi nel codice
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: 4cdcda7c5c78481af1633bf29d75070c521ab393
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347397"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>Parole chiave come nomi di elementi nel codice (Visual Basic)
Qualsiasi elemento del programma, ad esempio una variabile, una classe o un membro, può avere lo stesso nome di una parola chiave con restrizioni. Ad esempio, è possibile creare una variabile denominata `Loop`. Tuttavia, per fare riferimento alla relativa versione, che ha lo stesso nome della parola chiave `Loop` limitata, è necessario precederla con una stringa di qualificazione completa o racchiuderla tra parentesi quadre (`[ ]`), come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 Se non si esegue una di queste operazioni, Visual Basic presuppone l'uso della parola chiave intrinseca `Loop` e genera un errore, come nell'esempio seguente:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 È possibile utilizzare le parentesi quadre per fare riferimento a form e controlli e quando si dichiara una variabile o si definisce una routine con lo stesso nome di una parola chiave con restrizioni. Può essere facile dimenticare di qualificare i nomi o includere le parentesi quadre e quindi introdurre errori nel codice e renderlo più difficile da leggere. Per questo motivo, è consigliabile non usare parole chiave con restrizioni come nomi degli elementi del programma. Tuttavia, se una versione futura di Visual Basic definisce una parola chiave nuova che è in conflitto con un modulo o un nome di controllo esistente, è possibile utilizzare questa tecnica quando si aggiorna il codice per utilizzare la nuova versione.  
  
> [!NOTE]
> Il programma può inoltre includere i nomi degli elementi forniti da altri assembly a cui si fa riferimento. Se questi nomi sono in conflitto con parole chiave con restrizioni, l'inserimento di parentesi quadre attorno ad essi causa la Visual Basic di interpretarli come elementi definiti.  
  
## <a name="see-also"></a>Vedere anche

- [Convenzioni di denominazione Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
