---
title: Operatori booleani (F#)
description: 'Scopri gli operatori booleani che sono disponibili nel linguaggio di programmazione F #.'
ms.date: 05/16/2016
ms.openlocfilehash: faa181090efa7c4064a30b42d83afa4888e98b82
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44272319"
---
# <a name="boolean-operators"></a>Operatori booleani

In questo argomento viene descritto il supporto per gli operatori booleani nel linguaggio F #.

## <a name="summary-of-boolean-operators"></a>Riepilogo degli operatori booleani

Nella tabella seguente sono riepilogati gli operatori booleani che sono disponibili nel linguaggio F #. L'unico tipo supportato da questi operatori è il `bool` tipo.

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
