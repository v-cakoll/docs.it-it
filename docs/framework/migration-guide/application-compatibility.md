---
title: Modifiche di runtime e retargeting - .NET Framework
ms.date: 10/29/2019
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
ms.openlocfilehash: c46f781d495b87a4f24e77935df7c4814c8567ae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73196703"
---
# <a name="application-compatibility-in-the-net-framework"></a>Compatibilità delle applicazioni in .NET Framework

La compatibilità è un obiettivo importante di ogni versione di .NET. La compatibilità garantisce che ogni versione sia additiva, pertanto le versioni precedenti continueranno a funzionare. D'altra parte, le modifiche alle funzionalità precedenti (ad esempio, per migliorare le prestazioni, risolvere i problemi di sicurezza o correggere i bug) possono causare problemi di compatibilità nel codice esistente o nelle applicazioni esistenti eseguite in una versione successiva.

Ogni app è destinata a una versione specifica di .NET Framework tramite:

- Definizione di un framework di destinazione in Visual Studio.
- Indicazione del framework di destinazione in un file di progetto.
- Applicazione di un <xref:System.Runtime.Versioning.TargetFrameworkAttribute> al codice sorgente.

Quando si esegue la migrazione da una versione di .NET Framework a un'altra, è necessario considerare due tipi di modifiche:

- [Modifiche di runtime](#runtime-changes)
- [Modifiche di retargeting](#retargeting-changes)

## <a name="runtime-changes"></a>Modifiche in fase di esecuzione

I problemi di runtime sono quelli che si verificano quando un nuovo runtime viene inserito in un computer e il comportamento di un'app cambia. Quando viene eseguito su una versione più recente di quella di destinazione, .NET Framework utilizza un comportamento *anomalo* per simulare la versione di destinazione precedente. L'app viene eseguita nella versione più recente, ma funziona come se fosse in esecuzione nella versione precedente. Questo modello di comportamento consente di attenuare molti problemi di compatibilità tra versioni diverse di .NET Framework. Ad esempio, se un file binario è stato compilato per .NET Framework 4.0 ma viene eseguito in un computer con .NET Framework 4.5 o versione successiva, viene eseguito in modalità compatibilità .NET Framework 4.0. Ciò significa che molte delle modifiche nella versione successiva non influiscono sul file binario.

La versione di .NET Framework di destinazione di un'applicazione è determinata dalla versione di destinazione dell'assembly della voce per il dominio applicazione in cui viene eseguito il codice. Tutti gli assembly aggiuntivi caricati in tale dominio applicazione sono destinati a tale versione. Ad esempio, nel caso di un eseguibile, la versione che le destinazioni eseguibili è la modalità di compatibilità in cui vengono eseguiti tutti gli assembly in tale dominio applicazione.

Per visualizzare un elenco delle modifiche di runtime che si applicano all'ambiente, selezionare la versione di .NET Framework attualmente di destinazione e quindi la versione a cui si desidera eseguire la migrazione:

[!INCLUDE[versionselector](../../../includes/migration-guide/runtime/versionselector.md)]

## <a name="retargeting-changes"></a>Modifiche di reindirizzamento

Le modifiche di retargeting sono quelle che si verificano quando un assembly viene ricompilato per essere destinato a una versione più recente. La destinazione di una versione più recente significa che l'assembly attiva le nuove funzionalità e potenziali problemi di compatibilità per le funzionalità precedenti.

Per visualizzare un elenco delle modifiche di retargeting che si applicano all'ambiente, selezionare la versione di .NET Framework attualmente di destinazione e quindi la versione in cui si desidera eseguire la migrazione:

[!INCLUDE[versionselector](../../../includes/migration-guide/retargeting/versionselector.md)]

## <a name="impact-classification"></a>Classificazione d'impatto

Negli argomenti che descrivono le modifiche di runtime e retargeting, ad esempio, [il retargeting delle modifiche per la migrazione da 4.7.2 a 4.8](retargeting/4.7.2-4.8.md), i singoli elementi vengono classificati in base all'impatto previsto come indicato di seguito:

**Principali**\
Una modifica significativa che influisce su un numero elevato di app o che richiede variazioni sostanziali del codice.

**Minore**\
Una modifica che influisce su un numero ridotto di app o che richiede variazioni marginali del codice.

**Custodia per bordi**\
Una modifica che influisce sulle app in scenari molto specifici e non comuni.

**Trasparente**\
Una modifica che non ha effetti evidenti sullo sviluppatore o sull'utente dell'app. L'app non dovrebbe richiedere variazioni a causa di questa modifica.

## <a name="see-also"></a>Vedere anche

- [Versioni e dipendenze](versions-and-dependencies.md)
- [Novità](../whats-new/index.md)
- [Ciò che è obsoleto](../whats-new/whats-obsolete.md)
