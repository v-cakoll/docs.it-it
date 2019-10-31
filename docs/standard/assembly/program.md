---
title: Programmare con gli assembly
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
ms.openlocfilehash: 9f07d36d9e47189d53e367fd1406e5684c024aa3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107063"
---
# <a name="program-with-assemblies"></a>Programmare con gli assembly
Gli assembly sono i blocchi costitutivi di .NET Framework. Costituiscono la base per la distribuzione, il controllo della versione, il riutilizzo, la definizione dell'ambito di attivazione e le autorizzazioni di sicurezza. Un assembly offre a Common Language Runtime le informazioni necessarie per il riconoscimento delle implementazioni di tipi. È una raccolta di tipi e risorse creati per essere usati insieme e per formare un'unità logica di funzionalità. Per il runtime, un tipo non esiste all'esterno del contesto di un assembly.  
  
 Questa sezione descrive come creare moduli, come creare assembly da moduli, come creare una coppia di chiavi e firmare un assembly con un nome sicuro e infine come installare un assembly nella Global Assembly Cache. Questa sezione descrive anche come usare [MSIL Disassembler (Ildasm.exe)](../../framework/tools/ildasm-exe-il-disassembler.md) per visualizzare informazioni sul manifesto dell'assembly.  
  
> [!NOTE]
> A partire da .NET Framework versione 2.0 il runtime non caricherà un assembly compilato con una versione di .NET Framework con numero di versione superiore a quello del runtime attualmente caricato. Questo vale per la combinazione dei componenti numero principale e numero secondario del numero di versione.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Creazione di assembly](create.md)  
 Offre una panoramica degli assembly a file singolo e su più file.  
  
 [Nomi degli assembly](names.md)  
 Offre una panoramica dell'assegnazione dei nomi agli assembly.  
  
 [Procedura: determinare il nome completo di un assembly](find-fully-qualified-name.md)  
 Descrive come determinare il nome completo di un assembly.  
  
 [Esecuzione di applicazioni Intranet in attendibilità totale](../../framework/app-domains/running-intranet-applications-in-full-trust.md)  
 Descrive come specificare criteri di sicurezza legacy per assembly con attendibilità totale in una condivisione di rete Intranet.  
  
 [Percorso assembly](location.md)  
 Offre una panoramica della posizione in cui si trovano gli assembly.  
  
 [Procedura: compilare un assembly a file singolo](../../framework/app-domains/build-single-file-assembly.md)  
 Descrive come creare un assembly su singolo file.  
  
 [Assembly su più file](../../framework/app-domains/multifile-assemblies.md)  
 Descrive i motivi per la creazione di assembly su più file.  
  
 [Procedura: compilare un assembly su più file](../../framework/app-domains/build-multifile-assembly.md)  
 Descrive come creare un assembly su più file.  
  
 [Impostare gli attributi dell'assembly](set-attributes.md)  
 Descrive gli attributi dell'assembly e come impostarli.  
  
 [Creazione e utilizzo di assembly con nome sicuro](create-use-strong-named.md)  
 Descrive come e perché aggiungere un nome sicuro a un assembly e include procedure.  
  
 [Ritardare la firma di un assembly](delay-sign.md)  
 Descrive come ritardare la firma di un assembly.  
  
 [Usare gli assembly e i Global Assembly Cache](../../framework/app-domains/working-with-assemblies-and-the-gac.md)  
 Descrive come e perché aggiungere assembly alla Global Assembly Cache e include argomenti relativi a procedure.  
  
 [Procedura: visualizzare il contenuto dell'assembly](view-contents.md)  
 Descrive come usare MSIL Disassembler (Ildasm.exe) per visualizzare il contenuto dell'assembly.  
  
 [Invio del tipo nell'Common Language Runtime](type-forwarding.md)  
 Descrive come usare l'inoltro del tipo per spostare un tipo in un assembly diverso senza compromettere il funzionamento delle applicazioni esistenti.  
  
## <a name="reference"></a>Reference  
 <xref:System.Reflection.Assembly>  
 Classe di .NET Framework che rappresenta un assembly.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Procedura: ottenere informazioni sul tipo e sui membri da un assembly](../../framework/reflection-and-codedom/get-type-member-information.md)  
 Descrive come ottenere a livello di codice il tipo e altre informazioni relative a un assembly.  
  
 [Assembly in .NET](index.md)  
 Offre una panoramica concettuale sugli assembly Common Language Runtime.  
  
 [Controllo delle versioni degli assembly](versioning.md)  
 Offre una panoramica dell'associazione di assembly e degli attributi <xref:System.Reflection.AssemblyVersionAttribute> e <xref:System.Reflection.AssemblyInformationalVersionAttribute>.  
  
 [Come il runtime individua gli assembly](../../framework/deployment/how-the-runtime-locates-assemblies.md)  
 Descrive come il runtime determina l'assembly da usare per eseguire una richiesta di associazione.  
  
 [Reflection](../../framework/reflection-and-codedom/reflection.md)   
 Descrive come usare la classe **Reflection** per ottenere informazioni su un assembly.
