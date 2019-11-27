---
title: 'Procedura: creare una routine'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: a831814c18f97991fca8067f1c9c8e491da1b665
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344905"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>Procedura: creare una routine (Visual Basic)

È possibile racchiudere una procedura tra un'istruzione di dichiarazione iniziale (`Sub` o `Function`) e un'istruzione di dichiarazione finale (`End Sub` o `End Function`). Tutto il codice della procedura si trova tra queste istruzioni.

 Una routine non può contenere un'altra procedura, quindi le istruzioni iniziali e finali devono essere esterne a qualsiasi altra procedura.

 Se si dispone di codice che esegue la stessa attività in posizioni diverse, è possibile scrivere l'attività una sola volta come procedura e quindi chiamarla da posizioni diverse nel codice.

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>Per creare una routine che non restituisce un valore

1. Al di fuori di qualsiasi altra procedura, utilizzare un'istruzione `Sub` seguita da un'istruzione `End Sub`.

2. Nell'istruzione `Sub` seguire la parola chiave `Sub` con il nome della stored procedure, quindi l'elenco di parametri tra parentesi.

3. Inserire le istruzioni di codice della stored procedure tra le istruzioni `Sub` e `End Sub`.

### <a name="to-create-a-procedure-that-returns-a-value"></a>Per creare una routine che restituisce un valore

1. Al di fuori di qualsiasi altra procedura, utilizzare un'istruzione `Function` seguita da un'istruzione `End Function`.

2. Nell'istruzione `Function` seguire la parola chiave `Function` con il nome della procedura, quindi l'elenco di parametri tra parentesi e quindi una clausola `As` che specifica il tipo di dati del valore restituito.

3. Inserire le istruzioni di codice della stored procedure tra le istruzioni `Function` e `End Function`.

4. Utilizzare un'istruzione `Return` per restituire il valore al codice chiamante.

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>Per connettere la nuova procedura con i blocchi di codice precedenti e ripetitivi

1. Assicurarsi di definire la nuova procedura in una posizione in cui il codice precedente può accedervi.

2. Nel blocco di codice precedente e ripetitivo sostituire le istruzioni che eseguono l'attività ripetitiva con una singola istruzione che chiama la routine `Sub` o `Function`.

3. Se la routine è un `Function` che restituisce un valore, assicurarsi che l'istruzione chiamante esegua un'azione con il valore restituito, ad esempio archiviarla in una variabile, altrimenti il valore andrà perso.

## <a name="example"></a>Esempio

 La seguente procedura `Function` calcola il lato più lungo, o ipotenusa, di un triangolo rettangolo, dati i valori per gli altri due lati:

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
