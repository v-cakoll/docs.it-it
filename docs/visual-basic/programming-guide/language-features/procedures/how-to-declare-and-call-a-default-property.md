---
title: 'Procedura: Dichiarare e chiamare una proprietà predefinita'
ms.date: 07/20/2015
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
ms.openlocfilehash: 4de5d94a94e764d1fc543ffae41b00a9bb729c94
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388154"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic
Una *proprietà predefinita* è una proprietà di classe o struttura a cui il codice può accedere senza specificarlo. Quando si chiama il codice denomina una classe o una struttura ma non una proprietà e il contesto consente l'accesso a una proprietà, Visual Basic risolve l'accesso alla proprietà predefinita della classe o della struttura se ne esiste una.  
  
 Una classe o una struttura può includere al massimo una proprietà predefinita. Tuttavia, è possibile eseguire l'overload di una proprietà predefinita e avere più di una versione.  
  
 Per ulteriori informazioni, vedere [default](../../../language-reference/modifiers/default.md).  
  
### <a name="to-declare-a-default-property"></a>Per dichiarare una proprietà predefinita  
  
1. Dichiarare la proprietà in modo normale. Non specificare la `Shared` `Private` parola chiave o.  
  
2. Includere la `Default` parola chiave nella dichiarazione della proprietà.  
  
3. Specificare almeno un parametro per la proprietà. Non è possibile definire una proprietà predefinita che non accetta almeno un argomento.  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a>Per chiamare una proprietà predefinita  
  
1. Dichiarare una variabile della classe o del tipo di struttura che lo contiene.  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. Usare il nome della variabile da solo in un'espressione in cui in genere si include il nome della proprietà.  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. Seguire il nome della variabile con un elenco di argomenti tra parentesi. Una proprietà predefinita deve assumere almeno un argomento.  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. Per recuperare il valore predefinito della proprietà, usare il nome della variabile, con un elenco di argomenti, in un'espressione o dopo il `=` segno di uguale () in un'istruzione di assegnazione.  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. Per impostare il valore predefinito della proprietà, utilizzare il nome della variabile, con un elenco di argomenti, sul lato sinistro di un'istruzione di assegnazione.  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. È sempre possibile specificare il nome della proprietà predefinita insieme al nome della variabile, esattamente come si farebbe per accedere a qualsiasi altra proprietà.  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene dichiarata una proprietà predefinita per una classe.  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come chiamare la proprietà predefinita `myProperty` sulla classe `class1` . Le tre istruzioni di assegnazione archiviano i valori in `myProperty` e la <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> chiamata legge i valori.  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 L'utilizzo più comune di una proprietà predefinita è la <xref:Microsoft.VisualBasic.Collection.Item%2A> Proprietà in varie classi di raccolte.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le proprietà predefinite possono causare una riduzione ridotta dei caratteri di codice sorgente, ma possono rendere il codice più difficile da leggere. Se il codice chiamante non ha familiarità con la classe o la struttura, quando fa riferimento al nome della classe o della struttura, non può essere certo se il riferimento accede alla classe o alla struttura o a una proprietà predefinita. Questo può causare errori del compilatore o errori di logica di run-time sottili.  
  
 È possibile ridurre in qualche modo la probabilità di errori di proprietà predefiniti usando sempre l' [istruzione Option Strict](../../../language-reference/statements/option-strict-statement.md) per impostare il controllo dei tipi del compilatore su `On` .  
  
 Se si prevede di usare una classe o una struttura predefinita nel codice, è necessario determinare se dispone di una proprietà predefinita e, in caso affermativo, il nome.  
  
 A causa di questi svantaggi, è consigliabile non definire le proprietà predefinite. Per la leggibilità del codice, è consigliabile considerare sempre il riferimento a tutte le proprietà in modo esplicito, anche le proprietà predefinite.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Default](../../../language-reference/modifiers/default.md)
- [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)
- [Procedura: creare una proprietà](./how-to-create-a-property.md)
- [Procedura: dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedura: chiamare una routine di proprietà](./how-to-call-a-property-procedure.md)
- [Procedura: inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)
- [Procedura: ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
