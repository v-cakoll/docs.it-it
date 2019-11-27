---
title: 'Procedura: creare una routine che restituisce un valore'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 218dbb52abc0100724d38d10be91ef24252d5226
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349713"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>Procedura: creare una routine che restituisce un valore (Visual Basic)
Usare una procedura `Function` per restituire un valore al codice chiamante.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Per creare una routine che restituisce un valore  
  
1. Al di fuori di qualsiasi altra procedura, utilizzare un'istruzione `Function` seguita da un'istruzione `End Function`.  
  
2. Nell'istruzione `Function` seguire la parola chiave `Function` con il nome della stored procedure, quindi l'elenco di parametri tra parentesi.  
  
3. Seguire le parentesi con una clausola `As` per specificare il tipo di dati del valore restituito.  
  
4. Inserire le istruzioni di codice della stored procedure tra le istruzioni `Function` e `End Function`.  
  
5. Utilizzare un'istruzione `Return` per restituire il valore al codice chiamante.  
  
     La seguente procedura `Function` calcola il lato più lungo, o ipotenusa, di un triangolo rettangolo, dati i valori per gli altri due lati.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     Nell'esempio seguente viene illustrata una tipica chiamata a `hypotenuse`.  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Procedura: Restituire un valore da una routine](./how-to-return-a-value-from-a-procedure.md)
- [Procedura: Chiamare una routine che restituisce un valore](./how-to-call-a-procedure-that-returns-a-value.md)
