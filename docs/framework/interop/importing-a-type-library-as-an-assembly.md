---
title: Importazione di una libreria dei tipi come assembly
description: Importare una libreria dei tipi che contiene le definizioni dei tipi COM come assembly. Informazioni su come creare metadati da una libreria dei tipi, ottenendo un assembly di interoperabilità.
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- type metadata
- custom wrappers
- metadata
- exposing COM components to .NET Framework
- Type Library Importer
- interoperation with unmanaged code, importing type library
- interoperation with unmanaged code, exposing COM components
- type libraries
- TypeLibConverter class, importing type library as assembly
- COM interop, importing type library
- COM interop, exposing COM components
ms.assetid: d1898229-cd40-426e-a275-f3eb65fbc79f
ms.openlocfilehash: e5187e3c2ce533f25a38e93bc3715dd3e2e47c11
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622718"
---
# <a name="importing-a-type-library-as-an-assembly"></a>Importazione di una libreria dei tipi come assembly

In genere, le definizioni dei tipi COM sono incluse in una libreria dei tipi. Al contrario, i compilatori conformi a CLS producono metadati dei tipi in un assembly. Le due origini delle informazioni sui tipi sono piuttosto diverse. Questo argomento descrive le tecniche per la generazione di metadati da una libreria dei tipi. L'assembly risultante è definito un assembly di interoperabilità e le informazioni sui tipi che contiene permettono alle applicazioni .NET Framework di usare tipi COM.

Per rendere queste informazioni sui tipi disponibili all'applicazione, è possibile usare due modi diversi:

- Uso di assembly di interoperabilità solo in fase di progettazione: a partire dalla .NET Framework 4, è possibile indicare al compilatore di incorporare le informazioni sul tipo dall'assembly di interoperabilità nell'eseguibile. Il compilatore incorpora solo le informazioni sui tipi usate dall'applicazione. Non è necessario distribuire l'assembly di interoperabilità con l'applicazione. Questa è la tecnica consigliata.

- Distribuire assembly di interoperabilità: è possibile creare un riferimento standard all'assembly di interoperabilità. In questo caso, l'assembly di interoperabilità deve essere distribuito con l'applicazione. Se si ricorre a questa tecnica e non si usa un componente COM privato, fare sempre riferimento all'assembly di interoperabilità primario pubblicato dall'autore del componente COM che si intende incorporare nel codice gestito. Per altre informazioni sulla creazione e sull'uso di assembly di interoperabilità primari, vedere [Primary Interop Assemblies](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aax7sdch(v=vs.100)) (Assembly di interoperabilità primari).

Quando si usano assembly di interoperabilità solo in fase di progettazione, è possibile incorporare le informazioni sui tipi dall'assembly di interoperabilità primario pubblicato dall'autore del componente COM. Tuttavia, non è necessario distribuire l'assembly di interoperabilità primario con l'applicazione.

L'uso di assembly di interoperabilità primari solo in fase di progettazione permette di ridurre le dimensioni dell'applicazione, perché la maggior parte delle applicazioni non usa tutte le funzionalità di un componente COM. Il compilatore è molto efficiente quando incorpora le informazioni sui tipi: se l'applicazione usa solo alcuni dei metodi in un'interfaccia COM, il compilatore non incorpora quelli inutilizzati. Quando un'applicazione in cui sono incorporate informazioni sui tipi interagisce con un'altra applicazione di questo tipo o con un'applicazione che usa un assembly di interoperabilità primario, Common Language Runtime usa regole di equivalenza dei tipi per determinare se due tipi con lo stesso nome rappresentano lo stesso tipo COM. La conoscenza di queste regole non è necessaria per usare oggetti COM. Tuttavia, per altre informazioni sulle regole, vedere [Equivalenza dei tipi e tipi di interoperabilità incorporati](type-equivalence-and-embedded-interop-types.md).

## <a name="generating-metadata"></a>Generazione di metadati

Le librerie dei tipi COM possono essere file autonomi con estensione tlb, ad esempio Loanlib.tlb. Alcune librerie dei tipi sono incorporate nella sezione delle risorse di un file DLL o EXE. Altre origini per le librerie dei tipi sono i file OLB e OCX.

Dopo aver individuato la libreria dei tipi che contiene l'implementazione del tipo COM di destinazione, è possibile scegliere tra le opzioni seguenti per generare un assembly di interoperabilità contenente i metadati dei tipi:

- Visual Studio

  Visual Studio converte automaticamente i tipi COM in una libreria dei tipi in metadati in un assembly. Per istruzioni, vedere [procedura: aggiungere riferimenti alle librerie dei tipi](how-to-add-references-to-type-libraries.md).

- [Tlbimp.exe (utilità di importazione della libreria dei tipi)](../tools/tlbimp-exe-type-library-importer.md)

  L'utilità di importazione della libreria dei tipi offre opzioni della riga di comando per modificare i metadati nel file di interoperabilità risultante, importare tipi da una libreria dei tipi esistente e generare un assembly di interoperabilità e uno spazio dei nomi. Per istruzioni, vedere [Procedura: Generare assembly di interoperabilità da librerie dei tipi](how-to-generate-interop-assemblies-from-type-libraries.md)

- Classe <xref:System.Runtime.InteropServices.TypeLibConverter?displayProperty=nameWithType>

  Questa classe fornisce i metodi per convertire coclassi e interfacce in una libreria dei tipi in metadati in un assembly. La classe produce gli stessi metadati restituiti da Tlbimp.exe. Tuttavia, diversamente da Tlbimp.exe, la classe <xref:System.Runtime.InteropServices.TypeLibConverter> può convertire in metadati una libreria dei tipi in memoria.

- Wrapper personalizzati

  Quando una libreria dei tipi non è disponibile o corretta, un'opzione consiste nel creare una definizione duplicata della classe o dell'interfaccia nel codice sorgente gestito. È quindi necessario compilare il codice sorgente con un compilatore basato sul runtime per produrre metadati in un assembly.

  Per definire tipi COM manualmente, è necessario avere accesso agli elementi seguenti:

  - Descrizioni precise delle coclassi e delle interfacce da definire.

  - Compilatore, ad esempio il compilatore C#, in grado di generare le definizioni delle classi .NET Framework appropriate.

  - Conoscenza delle regole di conversione da librerie dei tipi ad assembly.

  La scrittura di un wrapper personalizzato è una tecnica avanzata. Per altre informazioni su come generare un wrapper personalizzato, vedere [Personalizzazione di wrapper standard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100)).

 Per altre informazioni sui processi di importazione di interoperabilità COM, vedere [Riepilogo della conversione da libreria dei tipi ad assembly](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100)).

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.TypeLibConverter>
- [Esposizione di componenti COM a .NET Framework](exposing-com-components.md)
- [Riepilogo della conversione da libreria dei tipi ad assembly](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))
- [Tlbimp.exe (utilità di importazione della libreria di tipi)](../tools/tlbimp-exe-type-library-importer.md)
- [Personalizzazione di wrapper standard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))
- [Uso dei tipi COM nel codice gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))
- [Compilazione di un progetto di interoperabilità](compiling-an-interop-project.md)
- [Distribuzione di una applicazione di interoperabilità](deploying-an-interop-application.md)
- [Procedura: Aggiungere riferimenti alle librerie dei tipi](how-to-add-references-to-type-libraries.md)
- [Procedura: Generare assembly di interoperabilità da librerie dei tipi](how-to-generate-interop-assemblies-from-type-libraries.md)
