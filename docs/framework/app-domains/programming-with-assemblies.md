---
title: Programmazione con gli assembly
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f6a20a2e678c10157fed7da6f5de9f3ffee0c9ad
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="programming-with-assemblies"></a>Programmazione con gli assembly
Gli assembly sono i blocchi costitutivi di .NET Framework. Costituiscono la base per la distribuzione, il controllo della versione, il riutilizzo, la definizione dell'ambito di attivazione e le autorizzazioni di sicurezza. Un assembly offre a Common Language Runtime le informazioni necessarie per il riconoscimento delle implementazioni di tipi. È una raccolta di tipi e risorse creati per essere usati insieme e per formare un'unità logica di funzionalità. Per il runtime, un tipo non esiste all'esterno del contesto di un assembly.  
  
 Questa sezione descrive come creare moduli, come creare assembly da moduli, come creare una coppia di chiavi e firmare un assembly con un nome sicuro e infine come installare un assembly nella Global Assembly Cache. Questa sezione descrive anche come usare [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) per visualizzare informazioni sul manifesto dell'assembly.  
  
> [!NOTE]
>  A partire da .NET Framework versione 2.0 il runtime non caricherà un assembly compilato con una versione di .NET Framework con numero di versione superiore a quello del runtime attualmente caricato. Questo vale per la combinazione dei componenti numero principale e numero secondario del numero di versione.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Creazione degli assembly](../../../docs/framework/app-domains/create-assemblies.md)  
 Offre una panoramica degli assembly a file singolo e su più file.  
  
 [Nomi degli assembly](../../../docs/framework/app-domains/assembly-names.md)  
 Offre una panoramica dell'assegnazione dei nomi agli assembly.  
  
 [Procedura: Determinare il nome completo di un assembly](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 Descrive come determinare il nome completo di un assembly.  
  
 [Esecuzione di applicazioni Intranet in attendibilità totale](../../../docs/framework/app-domains/running-intranet-applications-in-full-trust.md)  
 Descrive come specificare criteri di sicurezza legacy per assembly con attendibilità totale in una condivisione di rete Intranet.  
  
 [Posizione dell'assembly](../../../docs/framework/app-domains/assembly-location.md)  
 Offre una panoramica della posizione in cui si trovano gli assembly.  
  
 [Procedura: Compilare un assembly su singolo file](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)  
 Descrive come creare un assembly su singolo file.  
  
 [Assembly su più file](../../../docs/framework/app-domains/multifile-assemblies.md)  
 Descrive i motivi per la creazione di assembly su più file.  
  
 [Procedura: Compilare un assembly su più file](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 Descrive come creare un assembly su più file.  
  
 [Impostazione degli attributi dell'assembly](../../../docs/framework/app-domains/set-assembly-attributes.md)  
 Descrive gli attributi dell'assembly e come impostarli.  
  
 [Creazione e utilizzo degli assembly con nome sicuro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 Descrive come e perché aggiungere un nome sicuro a un assembly e include procedure.  
  
 [Ritardo della firma di un assembly](../../../docs/framework/app-domains/delay-sign-assembly.md)  
 Descrive come ritardare la firma di un assembly.  
  
 [Uso di assembly e della Global Assembly Cache](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 Descrive come e perché aggiungere assembly alla Global Assembly Cache e include argomenti relativi a procedure.  
  
 [Procedura: Visualizzare il contenuto dell'assembly](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 Descrive come usare MSIL Disassembler (Ildasm.exe) per visualizzare il contenuto dell'assembly.  
  
 [Inoltro dei tipi in Common Language Runtime](../../../docs/framework/app-domains/type-forwarding-in-the-common-language-runtime.md)  
 Descrive come usare l'inoltro del tipo per spostare un tipo in un assembly diverso senza compromettere il funzionamento delle applicazioni esistenti.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Reflection.Assembly>  
 Classe di .NET Framework che rappresenta un assembly.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Procedura: Reperire informazioni su tipo e membro da un assembly](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 Descrive come ottenere a livello di codice il tipo e altre informazioni relative a un assembly.  
  
 [Assembly in Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Offre una panoramica concettuale sugli assembly Common Language Runtime.  
  
 [Controllo delle versioni degli assembly](../../../docs/framework/app-domains/assembly-versioning.md)  
 Offre una panoramica dell'associazione di assembly e degli attributi <xref:System.Reflection.AssemblyVersionAttribute> e <xref:System.Reflection.AssemblyInformationalVersionAttribute>.  
  
 [Come il runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 Descrive come il runtime determina l'assembly da usare per eseguire una richiesta di associazione.  
  
 [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Descrive come usare la classe **Reflection** per ottenere informazioni su un assembly.
