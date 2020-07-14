---
title: Equivalenza del tipo e tipi di interoperabilità incorporati
description: Comprendere l'equivalenza del tipo tra i tipi .NET e i membri con un assembly gestito e i tipi COM incorporati in tale assembly. Per .NET 4 e versioni successive.
ms.date: 03/30/2017
helpviewer_keywords:
- type equivalence
- embedded interop types
- primary interop assemblies,not necessary in CLR version 4
- NoPIA
ms.assetid: 78892eba-2a58-4165-b4b1-0250ee2f41dc
ms.openlocfilehash: 2d572133c42f01af7d50f6f771588f5173853f9a
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86282008"
---
# <a name="type-equivalence-and-embedded-interop-types"></a>Equivalenza del tipo e tipi di interoperabilità incorporati

A partire da .NET Framework 4, Common Language Runtime supporta l'incorporamento di informazioni sui tipi COM direttamente negli assembly gestiti, anziché richiedere agli assembly gestiti di ottenere informazioni sui tipi COM dagli assembly di interoperabilità. Dato che le informazioni sui tipi incorporate includono solo i tipi e membri che vengono effettivamente usati da un assembly gestito, due assembly gestiti potrebbero avere viste diverse dello stesso tipo COM. Ogni assembly gestito a un oggetto <xref:System.Type> diverso per rappresentare la vista specifica del tipo COM. Common Language Runtime supporta l'equivalenza del tipo tra queste viste diverse per interfacce, strutture, enumerazioni e delegati.

Equivalenza del tipo significa che è possibile eseguire il cast di un oggetto COM passato da un assembly gestito a un altro sul tipo gestito appropriato nell'assembly ricevente.

> [!NOTE]
> L'equivalenza del tipo e i tipi di interoperabilità incorporati semplificano la distribuzione delle applicazioni e dei componenti aggiuntivi che usano componenti COM, perché non è necessario distribuire gli assembly di interoperabilità con le applicazioni. Gli sviluppatori di componenti COM condivisi devono ancora creare gli assembly di interoperabilità primari, se vogliono che i componenti possano essere usati da versioni precedenti di .NET Framework.

## <a name="type-equivalence"></a>Equivalenza del tipo

 L'equivalenza dei tipi COM è supportata per interfacce, strutture, enumerazioni e delegati. I tipi COM sono considerati equivalenti se vengono soddisfatte tutte le condizioni seguenti:

- I tipi sono entrambi interfacce o entrambi strutture o entrambi enumerazioni o entrambi delegati.

- I tipi hanno la stessa identità, come descritto nella sezione successiva.

- Entrambi i tipi sono idonei per l'equivalenza del tipo, come descritto nella sezione [contrassegno dei tipi com per l'equivalenza del tipo](#marking-com-types-for-type-equivalence) .

### <a name="type-identity"></a>Identità dei tipi

Due tipi vengono considerati aventi la stessa identità quando i relativi ambiti e identità corrispondono, in altre parole, se ognuno ha l'attributo <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> e i due attributi hanno proprietà <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> e <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> corrispondenti. Il confronto per <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> non applica la distinzione tra maiuscole e minuscole.

Se un tipo non ha l'attributo <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> oppure ha un attributo <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> che non specifica l'ambito e l'identificatore, il tipo può ancora essere considerato per l'equivalenza, come indicato di seguito:

- Per le interfacce viene usato il valore di <xref:System.Runtime.InteropServices.GuidAttribute> invece della proprietà <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A?displayProperty=nameWithType> e viene usata la proprietà <xref:System.Type.FullName%2A?displayProperty=nameWithType> (vale a dire il nome di tipo, incluso lo spazio dei nomi) invece della proprietà <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A?displayProperty=nameWithType>.

- Per le strutture, le enumerazioni e i delegati, viene usato l'attributo <xref:System.Runtime.InteropServices.GuidAttribute> dell'assembly contenitore invece della proprietà <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> e viene usata la proprietà <xref:System.Type.FullName%2A?displayProperty=nameWithType> al posto della proprietà <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A>.

### <a name="marking-com-types-for-type-equivalence"></a>Contrassegno dei tipi COM per l'equivalenza del tipo

 È possibile contrassegnare un tipo come idoneo per l'equivalenza del tipo in due modi:

- Applicare l'attributo <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> al tipo.

- Impostare il tipo come tipo di importazione COM. Un'interfaccia è un tipo di importazione COM se ha l'attributo <xref:System.Runtime.InteropServices.ComImportAttribute>. Un'interfaccia, una struttura, un'enumerazione o un delegato è un tipo di importazione COM se l'assembly in cui è definito ha l'attributo <xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Type.IsEquivalentTo%2A>
- [Uso dei tipi COM nel codice gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))
- [Importazione di una libreria dei tipi come assembly](importing-a-type-library-as-an-assembly.md)
