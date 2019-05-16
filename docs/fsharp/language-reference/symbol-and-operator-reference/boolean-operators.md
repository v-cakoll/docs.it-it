---
title: Operatori booleani
description: Scopri gli operatori booleani che sono disponibili in di F# linguaggio di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: ad4bdd1121389f7e280647dbe0c4d0098ffb17df
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641879"
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
