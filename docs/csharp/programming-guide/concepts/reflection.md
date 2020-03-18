---
title: Reflection (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: a56fb24b63e4d80dbb67b079466b67cd11672023
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74711666"
---
# <a name="reflection-c"></a>Reflection (C#)

La reflection fornisce <xref:System.Type>oggetti (di tipo ) che descrivono assembly, moduli e tipi. È possibile usare la reflection per creare in modo dinamico un'istanza di un tipo, associare il tipo a un oggetto esistente oppure ottenere il tipo da un oggetto esistente e richiamarne i metodi o accedere ai relativi campi e proprietà. Se si usano attributi nel codice, la reflection consente di accedervi. Per altre informazioni, vedere [Attributi](../../../standard/attributes/index.md).

Di seguito è riportato un <xref:System.Object.GetType> semplice esempio di reflection `Object` utilizzando il metodo , ereditato da tutti i tipi dalla classe base, per ottenere il tipo di una variabile:Here's a simple example of reflection using the method - inherited by all types from the base class - to obtain the type of a variable:

> [!NOTE]
> Assicurati di `using System;` aggiungere `using System.Reflection;` e nella parte superiore del file *.cs.*

```csharp
// Using GetType to obtain type information:
int i = 42;
Type type = i.GetType();
Console.WriteLine(type);
```

L'output `System.Int32`è: .

L'esempio seguente usa la reflection per ottenere il nome completo dell'assembly caricato.

```csharp
// Using Reflection to get information of an Assembly:
Assembly info = typeof(int).Assembly;
Console.WriteLine(info);
```

L'output `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`è: .

> [!NOTE]
> Le parole chiave di C# `protected` e `internal` non hanno significato in IL e non sono usate nelle API di reflection. I termini corrispondenti in IL sono *Famiglia* e *Assembly*. Per identificare un metodo `internal` tramite reflection, usare la proprietà <xref:System.Reflection.MethodBase.IsAssembly%2A>. Per identificare un metodo `protected internal`, usare <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.

## <a name="reflection-overview"></a>Panoramica della riflessione

La reflection è utile nelle situazioni seguenti:

- Quando è necessario accedere agli attributi nei metadati del programma. Per altre informazioni, vedere [Recupero di informazioni memorizzate negli attributi](../../../standard/attributes/retrieving-information-stored-in-attributes.md).
- Per esaminare e creare istanze di tipi in un assembly.
- Per creare nuovi tipi in fase di esecuzione. Usare le classi in <xref:System.Reflection.Emit>.
- Per eseguire l'associazione tardiva, accedere ai metodi per i tipi creati in fase di esecuzione. Vedere l'argomento relativo a [caricamento e uso dinamico dei tipi](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).

## <a name="related-sections"></a>Sezioni correlate

Per altre informazioni:

- [Riflessione](../../../framework/reflection-and-codedom/reflection.md)
- [Visualizzazione delle informazioni sul tipo](../../../framework/reflection-and-codedom/viewing-type-information.md)
- [Reflection e tipi generici](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)
- <xref:System.Reflection.Emit>
- [Recupero di informazioni memorizzate negli attributi](../../../standard/attributes/retrieving-information-stored-in-attributes.md)

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Assembly in .NET](../../../standard/assembly/index.md)
