---
title: 'Procedura: Creazione di una procedura (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 2cf4c788ec421c1e74ef7198496a92149e049752
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216727"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>Procedura: Creazione di una procedura (Visual Basic)

È possibile racchiudere una procedura tra un'istruzione di Dichiarazione`Sub` iniziale `Function`(o) e un'istruzione di`End Sub` Dichiarazione `End Function`finale (o). Tutto il codice della procedura si trova tra queste istruzioni.

 Una routine non può contenere un'altra procedura, quindi le istruzioni iniziali e finali devono essere esterne a qualsiasi altra procedura.

 Se si dispone di codice che esegue la stessa attività in posizioni diverse, è possibile scrivere l'attività una sola volta come procedura e quindi chiamarla da posizioni diverse nel codice.

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>Per creare una routine che non restituisce un valore

1. All'esterno di qualsiasi altra procedura, `Sub` utilizzare un'istruzione, seguita `End Sub` da un'istruzione.

2. Nell'istruzione seguire la `Sub` parola chiave con il nome della procedura, quindi l'elenco di parametri tra parentesi. `Sub`

3. Inserire le istruzioni di codice della stored procedure `Sub` tra `End Sub` le istruzioni e.

### <a name="to-create-a-procedure-that-returns-a-value"></a>Per creare una routine che restituisce un valore

1. All'esterno di qualsiasi altra procedura, `Function` utilizzare un'istruzione, seguita `End Function` da un'istruzione.

2. Nell'istruzione seguire la `Function` parola chiave con il nome della procedura, quindi l'elenco di parametri tra parentesi e quindi una `As` clausola che specifica il tipo di dati del valore restituito. `Function`

3. Inserire le istruzioni di codice della stored procedure `Function` tra `End Function` le istruzioni e.

4. Utilizzare un' `Return` istruzione per restituire il valore al codice chiamante.

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>Per connettere la nuova procedura con i blocchi di codice precedenti e ripetitivi

1. Assicurarsi di definire la nuova procedura in una posizione in cui il codice precedente può accedervi.

2. Nel blocco di codice precedente e ripetitivo sostituire le istruzioni che eseguono l'attività ripetitiva con una singola istruzione che chiama `Sub` la `Function` routine o.

3. Se la routine è una `Function` che restituisce un valore, assicurarsi che l'istruzione chiamante esegua un'azione con il valore restituito, ad esempio archiviarla in una variabile, altrimenti il valore andrà perso.

## <a name="example"></a>Esempio

 La procedura `Function` seguente calcola il lato più lungo, o ipotenusa, di un triangolo rettangolo, dati i valori per gli altri due lati:

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a>Vedere anche

- [Routine](index.md)
- [Routine Sub](sub-procedures.md)
- [Routine Function](function-procedures.md)
- [Routine Property](property-procedures.md)
- [Routine di operatore](operator-procedures.md)
- [Parametri e argomenti delle routine](procedure-parameters-and-arguments.md)
- [Routine ricorsive](recursive-procedures.md)
- [Overload della routine](procedure-overloading.md)
- [Oggetti e classi](../objects-and-classes/index.md)
- [Programmazione orientata a oggetti (Visual Basic)](../../concepts/object-oriented-programming.md)
