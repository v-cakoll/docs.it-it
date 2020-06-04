---
title: Clausola Join
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: f73dc31bbbb9014a8a1a315de406c53fa58d1c65
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359774"
---
# <a name="join-clause-visual-basic"></a>Clausola Join (Visual Basic)

Combina due raccolte in un'unica raccolta. L'operazione di join è basata sulle chiavi corrispondenti e usa l' `Equals` operatore.

## <a name="syntax"></a>Sintassi

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a>Parti

`element` Obbligatorio. Variabile di controllo per la raccolta da unire in join.

`collection`  
Obbligatorio. Raccolta da combinare con la raccolta identificata sul lato sinistro dell' `Join` operatore. Una `Join` clausola può essere annidata in un'altra `Join` clausola o in una `Group Join` clausola.

`joinClause`  
Facoltativa. Una o più `Join` clausole aggiuntive per perfezionare ulteriormente la query.

`groupJoinClause`  
Facoltativa. Una o più `Group Join` clausole aggiuntive per perfezionare ulteriormente la query.

`key1` `Equals` `key2`  
Obbligatorio. Identifica le chiavi per le raccolte da unire in join. `Equals`Per confrontare le chiavi delle raccolte da unire in join, è necessario usare l'operatore. È possibile combinare le condizioni di join usando l' `And` operatore per identificare più chiavi. `key1`deve derivare dalla raccolta a sinistra dell' `Join` operatore. `key2`deve derivare dalla raccolta a destra dell' `Join` operatore.

Le chiavi utilizzate nella condizione di join possono essere espressioni che includono più di un elemento della raccolta. Ogni espressione chiave può tuttavia contenere solo elementi della rispettiva raccolta.

## <a name="remarks"></a>Commenti

La `Join` clausola combina due raccolte in base ai valori di chiave corrispondenti delle raccolte da unire in join. La raccolta risultante può contenere qualsiasi combinazione di valori della raccolta identificata sul lato sinistro dell' `Join` operatore e della raccolta identificata nella `Join` clausola. La query restituirà solo i risultati per i quali viene soddisfatta la condizione specificata dall' `Equals` operatore. Equivale a un `INNER JOIN` in SQL.

È possibile utilizzare più `Join` clausole in una query per unire due o più raccolte in un'unica raccolta.

È possibile eseguire un join implicito per combinare raccolte senza la `Join` clausola. A tale scopo, includere più `In` clausole nella `From` clausola e specificare una `Where` clausola che identifichi le chiavi che si desidera utilizzare per il join.

È possibile usare la `Group Join` clausola per combinare le raccolte in un'unica raccolta gerarchica. Questa operazione è simile a `LEFT OUTER JOIN` in SQL.

## <a name="example"></a>Esempio

Nell'esempio di codice seguente viene eseguito un join implicito per combinare un elenco di clienti con i relativi ordini.

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a>Esempio

L'esempio di codice seguente unisce due raccolte usando la `Join` clausola.

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

In questo esempio verrà generato un output simile al seguente:

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a>Esempio

Nell'esempio di codice seguente vengono unite due raccolte utilizzando la `Join` clausola con due colonne chiave.

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

Nell'esempio viene generato un output simile al seguente:

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](index.md)
- [Clausola SELECT](select-clause.md)
- [Clausola from](from-clause.md)
- [Clausola Group Join](group-join-clause.md)
- [Clausola WHERE](where-clause.md)
