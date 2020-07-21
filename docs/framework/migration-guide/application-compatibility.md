---
title: Runtime e modifiche di reindirizzamento-.NET Framework
description: Informazioni sulla compatibilità delle applicazioni in .NET Framework e sul modo in cui sono interessati dal runtime e sulle modifiche di reindirizzamento durante la migrazione a un'altra versione.
ms.date: 10/29/2019
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
ms.openlocfilehash: 26f36dd34c6c5ecae8fc5ab373ff60d9e56f8245
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475489"
---
# <a name="application-compatibility-in-the-net-framework"></a>Compatibilità delle applicazioni nel .NET Framework

La compatibilità è un obiettivo importante di ogni versione di .NET. La compatibilità garantisce che ogni versione sia additiva, quindi le versioni precedenti continueranno a funzionare. D'altra parte, le modifiche apportate alle funzionalità precedenti, ad esempio per migliorare le prestazioni, risolvere i problemi di sicurezza o correggere i bug, possono causare problemi di compatibilità nel codice esistente o nelle applicazioni esistenti eseguite in una versione successiva.

Ogni app è destinata a una versione specifica del .NET Framework da:

- Definizione di un framework di destinazione in Visual Studio.
- Indicazione del framework di destinazione in un file di progetto.
- Applicazione di un <xref:System.Runtime.Versioning.TargetFrameworkAttribute> al codice sorgente.

Quando si esegue la migrazione da una versione del .NET Framework a un'altra, è necessario considerare due tipi di modifiche:

- [Modifiche in fase di esecuzione](#runtime-changes)
- [Modifiche di reindirizzamento](#retargeting-changes)

## <a name="runtime-changes"></a>Modifiche in fase di esecuzione

I problemi di runtime sono quelli che si verificano quando un nuovo runtime viene inserito in un computer e cambia il comportamento di un'app. Quando si esegue una versione più recente di quella di destinazione, il .NET Framework *utilizza un* comportamento anomalo per simulare la versione di destinazione precedente. L'app viene eseguita nella versione più recente, ma funziona come se fosse in esecuzione nella versione precedente. Questo modello di comportamento consente di attenuare molti problemi di compatibilità tra versioni diverse di .NET Framework. Ad esempio, se un file binario è stato compilato per .NET Framework 4,0 ma viene eseguito in un computer con .NET Framework 4,5 o versione successiva, viene eseguito in modalità di compatibilità .NET Framework 4,0. Ciò significa che molte delle modifiche apportate alla versione successiva non influiscono sul file binario.

La versione del .NET Framework a cui è destinata un'applicazione è determinata dalla versione di destinazione dell'assembly di immissione per il dominio dell'applicazione in cui viene eseguito il codice. Tutti gli assembly aggiuntivi caricati nel dominio applicazione sono destinati a tale versione. Nel caso di un eseguibile, ad esempio, la versione di destinazione dell'eseguibile è la modalità di compatibilità in cui vengono eseguiti tutti gli assembly del dominio applicazione.

Per visualizzare un elenco delle modifiche di runtime che si applicano all'ambiente in uso, selezionare la versione di .NET Framework attualmente destinata e quindi la versione a cui si vuole eseguire la migrazione:

[!INCLUDE[versionselector](../../../includes/migration-guide/runtime/versionselector.md)]

## <a name="retargeting-changes"></a>Modifiche di reindirizzamento

Le modifiche di reindirizzamento sono quelle che si verificano quando un assembly viene ricompilato per avere come destinazione una versione più recente. La definizione di una versione più recente indica che l'assembly sceglie le nuove funzionalità, nonché i potenziali problemi di compatibilità per le funzionalità obsolete.

Per visualizzare un elenco delle modifiche di reindirizzamento applicabili all'ambiente in uso, selezionare la versione .NET Framework attualmente destinata e quindi la versione a cui si vuole eseguire la migrazione:

[!INCLUDE[versionselector](../../../includes/migration-guide/retargeting/versionselector.md)]

## <a name="impact-classification"></a>Classificazione di effetto

Negli argomenti che descrivono le modifiche di runtime e di reindirizzamento, ad esempio le [modifiche di reindirizzamento per la migrazione da 4.7.2 a 4,8](retargeting/4.7.2-4.8.md), i singoli elementi vengono classificati in base all'effetto previsto, come indicato di seguito:

**Principali**\
Una modifica significativa che influisce su un numero elevato di app o che richiede variazioni sostanziali del codice.

**Secondaria**\
Una modifica che influisce su un numero ridotto di app o che richiede variazioni marginali del codice.

**Caso Edge**\
Una modifica che influisce sulle app in scenari molto specifici e non comuni.

**Trasparente**\
Una modifica che non ha effetti evidenti sullo sviluppatore o sull'utente dell'app. L'app non dovrebbe richiedere variazioni a causa di questa modifica.

## <a name="see-also"></a>Vedere anche

- [Versioni e dipendenze](versions-and-dependencies.md)
- [Novità](../whats-new/index.md)
- [Elementi obsoleti](../whats-new/whats-obsolete.md)
