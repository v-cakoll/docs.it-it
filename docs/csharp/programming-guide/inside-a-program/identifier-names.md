---
title: Nomi di identificatore
description: Informazioni sulle regole per assegnare un nome valido agli identificatori nel linguaggio di programmazione C#.
ms.date: 08/21/2018
ms.openlocfilehash: e5ff83661c9a86273760f32a795f7de6dbc7bf1d
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43877874"
---
# <a name="identifier-names"></a>Nomi di identificatore

Un **identificatore** è il nome assegnato a un tipo (classe, interfaccia, struct, delegato o enumerazione), un membro, una variabile o uno spazio dei nomi. Per essere validi gli identificatori devono rispettare le regole seguenti:

- Gli identificatori devono iniziare con una lettera o con `_`.
- Gli identificatori possono contenere caratteri alfabetici Unicode, cifre decimali, caratteri di connessione Unicode, caratteri combinati Unicode o caratteri di formattazione Unicode. Per altre informazioni sulle categorie Unicode, vedere [Unicode Category Database](https://www.unicode.org/reports/tr44/) (Database categorie Unicode).
È possibile dichiarare gli identificatori che corrispondono a parole chiave C# usando il prefisso `@` nell'identificatore. `@` non fa parte del nome dell'identificatore. Ad esempio, `@if` dichiara un identificatore denominato `if`. Questi [identificatori verbatim](../../language-reference/tokens/verbatim.md) servono principalmente per garantire l'interoperabilità con gli identificatori dichiarati in altri linguaggi.

Per una definizione completa degli identificatori validi, vedere l'[argomento sugli identificatori nelle specifiche del linguaggio C#](../../../../_csharplang/spec/lexical-structure.md#identifiers).

## <a name="naming-conventions"></a>Convenzioni di denominazione

Oltre alle regole, esiste una serie di [convenzioni di denominazione](../../../standard/design-guidelines/naming-guidelines.md) per gli identificatori, seguite in tutte le API .NET. Per convenzione, i programmi C# usano `PascalCase` per nomi di tipo, spazi dei nomi e tutti i membri pubblici. Sono anche comuni le convenzioni seguenti:

- I nomi di interfaccia iniziano con un carattere `I` maiuscolo.
- I tipi di attributo terminano con la parola `Attribute`.
- I tipi enumerazione usano un sostantivo singolare per non flag e uno plurale per flag.
- Gli identificatori non devono contenere due caratteri `_` consecutivi. Tali nomi sono riservati per gli identificatori generati dal compilatore.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Contenuto di un programma C#](../inside-a-program/index.md)
- [Riferimenti per C#](../../language-reference/index.md)
- [Classi](../classes-and-structs/classes.md)
- [Struct](../classes-and-structs/structs.md)
- [Spazi dei nomi](../namespaces/index.md)
- [Interfacce](../interfaces/index.md)
- [Delegati](../delegates/index.md)
