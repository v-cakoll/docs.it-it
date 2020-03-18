---
title: Tipi di riferimento - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: b2d6cc94c11ca6305a75e9ee489af53ad957201e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76744525"
---
# <a name="reference-types-c-reference"></a>Tipi di riferimento (Riferimenti per C#)

Esistono due generi di tipo in C#: tipi di riferimento e tipi di valore. Le variabili dei tipi di riferimento archiviano i riferimenti ai relativi dati (oggetti), mentre le variabili dei tipi di valore contengono direttamente i dati. Con i tipi di riferimento, due variabili possono fare riferimento allo stesso oggetto. Di conseguenza le operazioni su una variabile possono influire sull'oggetto a cui fa riferimento l'altra variabile. Con i tipi valore, ogni variabile ha una propria copia dei dati e non è possibile che le operazioni su una variabile influiscano sull'altra (tranne nel caso delle variabili dei parametri in, ref e out, vedere Modificatore del parametro [in](in-parameter-modifier.md), [ref](ref.md) e [out](out-parameter-modifier.md)).

 Le seguenti parole chiave vengono utilizzate per dichiarare i tipi di riferimento:

- [Classe](class.md)

- [Interfaccia](interface.md)

- [Delegato](../builtin-types/reference-types.md)

 In c# sono disponibili i seguenti tipi di riferimento predefiniti:

- [dinamico](../builtin-types/reference-types.md)

- [Oggetto](../builtin-types/reference-types.md)

- [Stringa](../builtin-types/reference-types.md)

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Parole chiave di C#](index.md)
- [Tipi di puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipi valore](../builtin-types/value-types.md)
