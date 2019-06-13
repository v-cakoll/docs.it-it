---
title: Migrazione da .NET Framework 1.1
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 4.5, migrating from 1.1
- .NET Framework 1.1, migrating to .NET Framework 4.5
ms.assetid: 7ead0cb3-3b19-414a-8417-a1c1fa198d9e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 441a65f9a72dd0fcffb062710df74bb529767cef
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816068"
---
# <a name="migrating-from-the-net-framework-11"></a>Migrazione da .NET Framework 1.1

[!INCLUDE[win7](../../../includes/win7-md.md)] e versioni successive del sistema operativo Windows non supportano .NET Framework 1.1. Di conseguenza, le applicazioni destinate a .NET Framework 1.1 non verranno eseguite senza modifica [!INCLUDE[win7](../../../includes/win7-md.md)] o versioni successive del sistema operativo. In questo argomento vengono illustrati i passaggi necessari per eseguire un'applicazione destinata a .NET Framework 1.1 in [!INCLUDE[win7](../../../includes/win7-md.md)] e versioni successive del sistema operativo Windows. Per altre informazioni su .NET Framework 1.1 e [!INCLUDE[win8](../../../includes/win8-md.md)], vedere [che eseguono .NET Framework 1.1 le App in Windows 8 e versioni successive](../../../docs/framework/install/run-net-framework-1-1-apps.md).

## <a name="retargeting-or-recompiling"></a>Reindirizzamento o ricompilazione

Esistono due modi per ottenere un'applicazione che è stata compilata con .NET Framework 1.1 per eseguire in [!INCLUDE[win7](../../../includes/win7-md.md)] o un sistema operativo Windows successivo:

- È possibile ridestinare l'applicazione per l'esecuzione in .NET Framework 4 e versioni successive. La ridestinazione richiede l'aggiunta di un elemento [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) al file di configurazione dell'applicazione che ne consenta l'esecuzione in .NET Framework 4 e versioni successive. Tale file di configurazione prende il form seguente:

    ```xml
    <configuration>
       <startup>
          <supportedRuntime version="v4.0"/>
       </startup>
    </configuration>
    ```

- È possibile ricompilare l'applicazione con un compilatore destinato a .NET Framework 4 o versioni successive. Se è stato originariamente usato Visual Studio 2003 per sviluppare e compilare la soluzione, è possibile aprirla in Visual Studio 2010 (ed eventualmente anche nelle versioni successive) e usare la finestra di dialogo **Compatibilità del progetto** per convertire la soluzione e i file di progetto dai formati usati da Visual Studio 2003 al formato Microsoft Build Engine (MSBuild).

Indipendentemente dal fatto che si preferisca ricompilare o reindirizzare l'applicazione, è necessario determinare se l'applicazione è interessata dalle modifiche introdotte in versioni successive di .NET Framework. Queste modifiche sono di due tipi:

- Modifiche importanti apportate tra il .NET Framework 1.1 e versioni successive di .NET Framework.

- Tipi e membri dei tipi che sono stati contrassegnati come deprecati o obsoleti tra il .NET Framework 1.1 e versioni successive di .NET Framework.

Se si Ridestina l'applicazione o si ricompila, è necessario esaminare sia le modifiche di rilievo e i tipi e membri obsoleti per ogni versione di .NET Framework successiva a .NET Framework 1.1.

## <a name="breaking-changes"></a>Modifiche di interruzione

Quando si verifica una modifica di interruzione, in base alla modifica specifica, è possibile che sia disponibile una soluzione alternativa sia per le applicazioni reindirizzate che per le applicazioni ricompilate. In alcuni casi, è possibile aggiungere un elemento figlio all'elemento [\<runtime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) del file di configurazione dell'applicazione per ripristinare il comportamento precedente. Ad esempio, il file di configurazione seguente ripristina l'ordinamento e comportamento del confronto utilizzato in .NET Framework 1.1 e può essere usato con una destinazione o un'applicazione ricompilata.

```xml
<configuration>
   <runtime>
      <CompatSortNLSVersion enabled="4096"/>
   </runtime>
</configuration>
```

Tuttavia, in alcuni casi, potrebbe essere necessario modificare il codice sorgente e ricompilare l'applicazione.

Per stimare l'impatto di possibili modifiche di interruzione sull'applicazione, è necessario rivedere i seguenti elenchi di modifiche:

- [Modifiche di rilievo in .NET Framework 2.0](https://go.microsoft.com/fwlink/?LinkId=125263) documenta le modifiche in .NET Framework 2.0 SP1 che possono interessare un'applicazione destinata a .NET Framework 1.1.

- [Le modifiche in .NET Framework 3.5 SP1](https://go.microsoft.com/fwlink/?LinkID=186989) documenta le modifiche tra .NET Framework 3.5 e [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)].

- In [Problemi di migrazione di .NET Framework 4](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md) sono descritte le modifiche tra [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] e .NET Framework 4.

## <a name="obsolete-types-and-members"></a>Tipi e membri obsoleti

L'impatto di tipi e membri deprecati è piuttosto diverso per le applicazioni reindirizzate e quelle ricompilate. L'utilizzo di tipi e membri obsoleti non influirà su un'applicazione reindirizzata a meno che il tipo o il membro obsoleto non siano stati fisicamente rimossi dall'assembly. La ricompilazione di un'applicazione che usa tipi o membri obsoleti di solito produce un avviso del compilatore piuttosto che un errore del compilatore. Tuttavia, in alcuni casi, produce un errore del compilatore e il codice che usa il tipo o il membro obsoleto non esegue correttamente la compilazione. In questo caso, è necessario riscrivere il codice sorgente che chiama il tipo o il membro obsoleto prima di ricompilare l'applicazione. Per altre informazioni sui tipi e sui membri obsoleti, vedere [Elementi obsoleti nella libreria di classi](../../../docs/framework/whats-new/whats-obsolete.md).

Per valutare l'impatto di tipi e membri deprecati fin dalla versione di .NET Framework 2.0 SP1, vedere [What ' s obsoleti nella libreria di classi .NET Framework](../../../docs/framework/whats-new/whats-obsolete.md). Esaminare l'elenco di tipi e membri obsoleti per .NET Framework 2.0 SP1 di .NET Framework 3.5 e .NET Framework 4.
