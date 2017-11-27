---
title: Operatori booleani (F#)
description: 'Scopri gli operatori booleani sono disponibili in F # linguaggio di programmazione.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f79370b8-4bc2-4704-b514-d392c80942bd
ms.openlocfilehash: 63588f2e371bf2c0f15de0b8a26a46be82f832c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
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
