---
title: Operatori booleani
description: Scopri gli operatori booleani che sono disponibili in di F# linguaggio di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: 5353b6ec6a0bd610f3446761a1d28f01f0403302
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612738"
---
# <a name="boolean-operators"></a>Operatori booleani

In questo argomento viene descritto il supporto per gli operatori booleani in di F# linguaggio.

## <a name="summary-of-boolean-operators"></a>Riepilogo degli operatori booleani

Nella tabella seguente sono riepilogati gli operatori booleani che sono disponibili in di F# linguaggio. L'unico tipo supportato da questi operatori è il `bool` tipo.

|Operatore|Descrizione|
|--------|-----------|
|`not`|Negazione booleana|
|<code>&#124;&#124;</code>|OR booleano|
|`&&`|AND booleano|

Il booleani AND e OR operatori seguire *valutazione di corto circuito*, vale a dire, tali operatori valutano l'espressione a destra dell'operatore solo quando è necessario determinare il risultato complessivo dell'espressione. La seconda espressione del `&&` operatore viene valutato solo se la prima espressione viene valutata `true`; la seconda espressione delle `||` operatore viene valutato solo se la prima espressione viene valutata `false`.

## <a name="see-also"></a>Vedere anche

- [Operatori bit per bit](bitwise-operators.md)
- [Operatori aritmetici](arithmetic-operators.md)
- [Riferimenti per simboli e operatori](index.md)