---
title: Migrazione da .NET Framework 1.1
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 4.5, migrating from 1.1
- .NET Framework 1.1, migrating to .NET Framework 4.5
ms.assetid: 7ead0cb3-3b19-414a-8417-a1c1fa198d9e
ms.openlocfilehash: 11fe9ba36d32a4c9fe363b48f76a8bb2b24f073b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73974962"
---
# <a name="migrate-from-the-net-framework-11"></a>Eseguire la migrazione da .NET Framework 1.1

Windows 7 e versioni successive del sistema operativo Windows non supportano .NET Framework 1.1. Di conseguenza, le applicazioni destinate a .NET Framework 1.1 non verranno eseguite senza modifiche in Windows 7 o versioni successive del sistema operativo. In questo argomento vengono illustrati i passaggi necessari per eseguire un'applicazione destinata a .NET Framework 1.1 in Windows 7 e versioni successive del sistema operativo Windows. Per ulteriori informazioni su .NET Framework 1.1 e Windows 8, vedere [Eseguire app di .NET Framework 1.1 in Windows 8 e versioni successive.](../install/run-net-framework-1-1-apps.md)

## <a name="retarget-or-recompile"></a>Ridestinazione o ricompilazione

Esistono due modi per ottenere un'applicazione che è stata compilata utilizzando .NET Framework 1.1 per l'esecuzione in Windows 7 o un sistema operativo Windows successivo:

- Ridestinare la destinazione dell'applicazione per l'esecuzione in .NET Framework 4 e versioni successive. Il retargeting richiede [ \<](../configure-apps/file-schema/startup/supportedruntime-element.md) l'aggiunta di un elemento>supportedRuntime al file di configurazione dell'applicazione che ne consenta l'esecuzione in .NET Framework 4 e versioni successive. Tale file di configurazione prende il form seguente:

    ```xml
    <configuration>
       <startup>
          <supportedRuntime version="v4.0"/>
       </startup>
    </configuration>
    ```

- Ricompilare l'applicazione con un compilatore destinato a .NET Framework 4 o versione successiva. Se è stato originariamente usato Visual Studio 2003 per sviluppare e compilare la soluzione, è possibile aprirla in Visual Studio 2010 (ed eventualmente anche nelle versioni successive) e usare la finestra di dialogo **Compatibilità del progetto** per convertire la soluzione e i file di progetto dai formati usati da Visual Studio 2003 al formato Microsoft Build Engine (MSBuild).

Indipendentemente dal fatto che si preferisca ricompilare o reindirizzare l'applicazione, è necessario determinare se l'applicazione è interessata dalle modifiche introdotte in versioni successive di .NET Framework. Queste modifiche sono di due tipi:

- Le modifiche di interruzione che si verificano tra .NET Framework 1.1 e le versioni successive di .NET Framework.

- I tipi e i membri del tipo contrassegnati come deprecati od obsoleti tra .NET Framework 1.1 e le versioni successive di .NET Framework.

Se si reindirizza o si ricompila l'applicazione, è necessario rivedere sia le modifiche di interruzione e i tipi e i membri obsoleti per ogni versione di .NET Framework rilasciata dopo .NET Framework 1.1.

## <a name="breaking-changes"></a>Modifiche di rilievo

Quando si verifica una modifica di interruzione, in base alla modifica specifica, è possibile che sia disponibile una soluzione alternativa sia per le applicazioni reindirizzate che per le applicazioni ricompilate. In alcuni casi, è possibile aggiungere un elemento figlio al [ \<runtime>](../configure-apps/file-schema/startup/supportedruntime-element.md) elemento del file di configurazione dell'applicazione per ripristinare il comportamento precedente. Ad esempio, nel file di configurazione seguente viene ripristinato l'ordinamento della stringa e il comportamento del confronto usato in .NET Framework 1.1 che può essere usato con un'applicazione reindirizzata o ricompilata.

```xml
<configuration>
   <runtime>
      <CompatSortNLSVersion enabled="4096"/>
   </runtime>
</configuration>
```

Tuttavia, in alcuni casi, potrebbe essere necessario modificare il codice sorgente e ricompilare l'applicazione.

Per stimare l'impatto di possibili modifiche di interruzione sull'applicazione, è necessario rivedere i seguenti elenchi di modifiche:

- Modifiche ai documenti relative alle [Modifiche sostanziali in .NET Framework 2.0](https://docs.microsoft.com/previous-versions/aa570326(v=msdn.10)) in .NET Framework 2.0 SP1 che possono interessare un'applicazione destinata a .NET Framework 1.1.

- In [Modifiche in .NET Framework 3.5 SP1](https://docs.microsoft.com/previous-versions/dotnet/articles/dd310284(v=msdn.10)) sono documentate le modifiche tra .NET Framework 3.5 e .NET Framework 3.5 SP1.

- In [Problemi di migrazione di .NET Framework 4](net-framework-4-migration-issues.md) sono documentate le modifiche tra .NET Framework 3.5 SP1 e .NET Framework 4.

## <a name="obsolete-types-and-members"></a>Tipi e membri obsoleti

L'impatto di tipi e membri deprecati è piuttosto diverso per le applicazioni reindirizzate e quelle ricompilate. L'utilizzo di tipi e membri obsoleti non influirà su un'applicazione reindirizzata a meno che il tipo o il membro obsoleto non siano stati fisicamente rimossi dall'assembly. La ricompilazione di un'applicazione che usa tipi o membri obsoleti di solito produce un avviso del compilatore piuttosto che un errore del compilatore. Tuttavia, in alcuni casi, produce un errore del compilatore e il codice che usa il tipo o il membro obsoleto non esegue correttamente la compilazione. In questo caso, è necessario riscrivere il codice sorgente che chiama il tipo o il membro obsoleto prima di ricompilare l'applicazione. Per altre informazioni sui tipi e sui membri obsoleti, vedere [Elementi obsoleti nella libreria di classi](../whats-new/whats-obsolete.md).

Per stimare l'impatto di tipi e membri deprecati fin dalla versione di .NET Framework 2.0 SP1, vedere [Elementi obsoleti nella libreria di classi](../whats-new/whats-obsolete.md). Rivedere gli elenchi di tipi e membri obsoleti per .NET Framework 2.0 SP1, .NET Framework 3.5 e .NET Framework 4.
