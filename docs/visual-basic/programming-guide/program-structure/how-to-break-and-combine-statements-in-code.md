---
title: 'Procedura: Interrompere e combinare istruzioni nel codice'
ms.date: 07/20/2015
f1_keywords:
- vb._
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
ms.openlocfilehash: c78cbeaa5c2df2d4f2e3cce2b5b3fb8048ff3388
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403252"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>Procedura: Interrompere e combinare istruzioni nel codice (Visual Basic)

Quando si scrive il codice, è possibile creare a volte istruzioni lunghe che richiedono lo scorrimento orizzontale nell'editor di codice. Sebbene questa operazione non influisca sul modo in cui viene eseguito il codice, è difficile per l'utente o per chiunque legga il codice visualizzato sul monitor. In questi casi, è consigliabile suddividere la singola istruzione Long in più righe.

## <a name="to-break-a-single-statement-into-multiple-lines"></a>Per suddividere una singola istruzione in più righe

Utilizzare il carattere di continuazione di riga, ovvero un carattere di sottolineatura ( `_` ), nel punto in cui si desidera che la riga si interrompa. Il carattere di sottolineatura deve essere immediatamente preceduto da uno spazio e seguito da un terminatore di riga (ritorno a capo) o (a partire dalla versione 16,0) di un commento seguito da un ritorno a capo.

  > [!NOTE]
  > In alcuni casi, se si omette il carattere di continuazione di riga, il Visual Basic compilatore continuerà in modo implicito l'istruzione alla riga di codice successiva. Per un elenco degli elementi della sintassi per i quali è possibile omettere il carattere di continuazione di riga, vedere "continuazione di riga implicita" nelle [istruzioni](../language-features/statements.md).

  Nell'esempio seguente l'istruzione è suddivisa in quattro righe con caratteri di continuazione di riga che terminano tutti tranne l'ultima riga.

  [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]

  L'uso di questa sequenza rende il codice più facile da leggere, sia online che quando viene stampato.

  Il carattere di continuazione di riga deve essere l'ultimo carattere su una riga. Non è possibile seguire altre operazioni sulla stessa riga.

  Esistono alcune limitazioni per la posizione in cui è possibile utilizzare il carattere di continuazione di riga; ad esempio, non è possibile usarlo nel mezzo di un nome di argomento. È possibile suddividere un elenco di argomenti con il carattere di continuazione di riga, ma i singoli nomi degli argomenti devono rimanere intatti.

  Non è possibile continuare un commento usando un carattere di continuazione di riga. Il compilatore non esamina i caratteri in un commento per un significato speciale. Per un commento su più righe, ripetere il simbolo di commento ( `'` ) in ogni riga.

 Sebbene ogni istruzione venga posizionata in una riga distinta è il metodo consigliato, Visual Basic consente anche di inserire più istruzioni nella stessa riga.

## <a name="to-place-multiple-statements-on-the-same-line"></a>Per inserire più istruzioni nella stessa riga

Separare le istruzioni con i due punti ( `:` ), come nell'esempio seguente:

  [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]

## <a name="see-also"></a>Vedere anche

- [Struttura del programma e convenzioni del codice](program-structure-and-code-conventions.md)
- [Istruzioni](../language-features/statements.md)
