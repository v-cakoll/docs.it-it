---
title: Tipi di riferimento (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: f99415fc9a2b728917cdf829ffb9e25823a824dd
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45609554"
---
# <a name="reference-types-c-reference"></a>Tipi di riferimento (Riferimenti per C#)

Esistono due generi di tipo in C#: tipi di riferimento e tipi di valore. Le variabili dei tipi di riferimento archiviano i riferimenti ai relativi dati (oggetti), mentre le variabili dei tipi di valore contengono direttamente i dati. Con i tipi di riferimento, due variabili possono fare riferimento allo stesso oggetto. Di conseguenza le operazioni su una variabile possono influire sull'oggetto a cui fa riferimento l'altra variabile. Con i tipi valore, ogni variabile ha una propria copia dei dati e non è possibile che le operazioni su una variabile influiscano sull'altra (tranne nel caso delle variabili dei parametri in, ref e out, vedere Modificatore del parametro [in](in-parameter-modifier.md), [ref](ref.md) e [out](out-parameter-modifier.md)).

 Le seguenti parole chiave vengono utilizzate per dichiarare i tipi di riferimento:

- [class](class.md)

- [interface](interface.md)

- [delegate](delegate.md)

 In c# sono disponibili i seguenti tipi di riferimento predefiniti:

- [dynamic](dynamic.md)

- [object](object.md)

- [string](string.md)

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Tipi](types.md)
- [Tipi valore](value-types.md)