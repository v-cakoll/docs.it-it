---
title: Operatori booleani (F#)
description: 'Scopri gli operatori booleani sono disponibili in F # linguaggio di programmazione.'
ms.date: 05/16/2016
ms.openlocfilehash: f8516ceb531907400f98dc4226d2985d3119e9e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="boolean-operators"></a>Operatori booleani

In questo argomento viene descritto il supporto per gli operatori booleani nel linguaggio F #.


## <a name="summary-of-boolean-operators"></a>Riepilogo degli operatori booleani
Nella tabella seguente sono riepilogati gli operatori booleani sono disponibili nel linguaggio F #. L'unico tipo supportato da questi operatori è il `bool` tipo.

|Operatore|Descrizione|
|--------|-----------|
|`not`|Negazione booleana|
|<code>&#124;&#124;</code>|Booleano OR|
|`&&`|Booleano AND|

Eseguono il booleani AND e OR operatori *valutazione di corto circuito*, vale a dire valutano l'espressione a destra dell'operatore solo quando è necessario determinare il risultato complessivo dell'espressione. La seconda espressione del `&&` operatore viene valutato solo se la prima espressione restituisce `true`; la seconda espressione del `||` operatore viene valutato solo se la prima espressione restituisce `false`.

## <a name="see-also"></a>Vedere anche
[Operatori bit per bit](bitwise-operators.md)

[Operatori aritmetici](arithmetic-operators.md)

[Riferimenti per simboli e operatori](index.md)
