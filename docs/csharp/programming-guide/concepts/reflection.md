---
title: Reflection (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: a56fb24b63e4d80dbb67b079466b67cd11672023
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711666"
---
# <a name="reflection-c"></a>Reflection (C#)

La reflection fornisce oggetti (di tipo <xref:System.Type>) che descrivono assembly, moduli e tipi. È possibile usare la reflection per creare in modo dinamico un'istanza di un tipo, associare il tipo a un oggetto esistente oppure ottenere il tipo da un oggetto esistente e richiamarne i metodi o accedere ai relativi campi e proprietà. Se si usano attributi nel codice, la reflection consente di accedervi. Per altre informazioni, vedere [Attributi](../../../standard/attributes/index.md).

Ecco un semplice esempio di reflection che usa il metodo <xref:System.Object.GetType> ereditato da tutti i tipi della classe di base `Object` per ottenere il tipo di una variabile:

> [!NOTE]
> Assicurarsi di aggiungere `using System;` e `using System.Reflection;` nella parte superiore del file con *estensione cs* .

```csharp
// Using GetType to obtain type information:
int i = 42;
Type type = i.GetType();
Console.WriteLine(type);
```

L'output è: `System.Int32`.

L'esempio seguente usa la reflection per ottenere il nome completo dell'assembly caricato.

```csharp
// Using Reflection to get information of an Assembly:
Assembly info = typeof(int).Assembly;
Console.WriteLine(info);
```

L'output è: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.

> [!NOTE]
> Le parole chiave di C# `protected` e `internal` non hanno significato in IL e non sono usate nelle API di reflection. I termini corrispondenti in IL sono *Famiglia* e *Assembly*. Per identificare un metodo `internal` tramite reflection, usare la proprietà <xref:System.Reflection.MethodBase.IsAssembly%2A>. Per identificare un metodo `protected internal`, usare <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.

## <a name="reflection-overview"></a>Panoramica della reflection

La reflection è utile nelle situazioni seguenti:

- Quando è necessario accedere agli attributi nei metadati del programma. Per altre informazioni, vedere [Recupero di informazioni memorizzate negli attributi](../../../standard/attributes/retrieving-information-stored-in-attributes.md).
- Per esaminare e creare istanze di tipi in un assembly.
- Per creare nuovi tipi in fase di esecuzione. Usare le classi in <xref:System.Reflection.Emit>.
- Per eseguire l'associazione tardiva, accedere ai metodi per i tipi creati in fase di esecuzione. Vedere l'argomento relativo a [caricamento e uso dinamico dei tipi](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).

## <a name="related-sections"></a>Sezioni correlate

Per ulteriori informazioni:

- [Reflection](../../../framework/reflection-and-codedom/reflection.md)
- [Visualizzazione delle informazioni sul tipo](../../../framework/reflection-and-codedom/viewing-type-information.md)
- [Reflection e tipi generici](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)
- <xref:System.Reflection.Emit>
- [Recupero di informazioni memorizzate negli attributi](../../../standard/attributes/retrieving-information-stored-in-attributes.md)

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Assembly in .NET](../../../standard/assembly/index.md)
