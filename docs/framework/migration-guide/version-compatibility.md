---
title: Compatibilità delle versioni in .NET Framework
ms.custom: updateeachrelease
ms.date: 04/02/2019
helpviewer_keywords:
- .NET Framework, version compatibility
- .NET Framework, compatibility with earlier versions
- .NET Framework versions, compatibility
ms.assetid: 2f25e522-456a-48c3-8a53-e5f39275649f
ms.openlocfilehash: 2e268753bf5941e9d28ee2bdd82ce77016ddf01a
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102983"
---
# <a name="version-compatibility"></a>Compatibilità tra versioni

Per compatibilità con le versioni precedenti si intende che un'app sviluppata per una particolare versione di una piattaforma sarà eseguita su versioni successive di quella piattaforma. .NET Framework tenta di ottimizzare la compatibilità con le versioni precedenti: il codice sorgente scritto per una versione di .NET Framework deve essere compilato nelle versioni successive di .NET Framework e i file binari eseguiti in una versione di .NET Framework devono comportarsi in modo identico nelle versioni successive di .NET Framework.

## <a name="version-compatibility-for-apps"></a><a name="Apps"></a> Compatibilità tra le versioni per app

Per impostazione predefinita, un'app viene eseguita nella versione di .NET Framework per cui è stata compilata. Se tale versione non è presente e il file di configurazione dell'app non definisce le versioni supportate, potrebbe verificarsi un errore di inizializzazione di .NET Framework. In questo caso, il tentativo di esecuzione dell'app avrà esito negativo.

Per definire le versioni specifiche in cui viene [ \<](../configure-apps/file-schema/startup/supportedruntime-element.md) eseguita l'app, aggiungi uno o più elementi di>supportedRuntime al file di configurazione dell'app. Ogni elemento `<supportedRuntime>` elenca una versione supportata del runtime, con il primo che specifica la versione preferita e l'ultimo che specifica l'ultima versione nell'elenco delle preferenze.

```xml
<configuration>
   <startup>
      <supportedRuntime version="v2.0.50727" />
      <supportedRuntime version="v4.0" />
   </startup>
</configuration>
```

Per altre informazioni, vedere [Procedura: Configurare un'app per supportare .NET Framework 4 o 4.x](../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md).

## <a name="version-compatibility-for-components"></a>Compatibilità tra le versioni per componenti

Un'app, diversamente da un componente, può controllare la versione di .NET Framework in cui viene eseguita. I componenti e le librerie di classi vengono caricati nel contesto di un'app specifica, ecco perché vengono eseguiti automaticamente nella versione di .NET Framework in cui è in esecuzione l'app.

A causa di questa restrizione, le garanzie di compatibilità sono particolarmente importanti per i componenti. A partire da .NET Framework 4, è possibile specificare il livello di compatibilità di un componente in più versioni applicando l'attributo <xref:System.Runtime.Versioning.ComponentGuaranteesAttribute?displayProperty=nameWithType> a tale componente. Gli strumenti possono usare questo attributo per rilevare le possibili violazioni della garanzia di compatibilità in versioni future di un componente.

## <a name="backward-compatibility"></a>compatibilità con versioni precedenti

.NET Framework 4.5 e versioni successive sono compatibili con le versioni precedenti delle app create con le versioni precedenti di .NET Framework. In altre parole, le app e i componenti creati con le versioni precedenti funzioneranno senza applicare alcuna modifica in .NET Framework 4.5 e versioni successive. Tuttavia, per impostazione predefinita, le app vengono eseguite sulla versione di Common Language Runtime per la quale sono state sviluppate, pertanto potrebbe essere necessario fornire un file di configurazione per far sì che l'app venga eseguita in .NET Framework 4.5 o versioni successive. Per altre informazioni, vedere la sezione [Compatibilità tra le versioni per app](#Apps) in questo articolo.

In pratica, questa compatibilità può essere interrotta da modifiche apparentemente irrilevanti in .NET Framework e nelle tecniche di programmazione. Ad esempio, i miglioramenti delle prestazioni in .NET Framework 4.5 possono esporre una race condition che non si era verificata nelle versioni precedenti. Allo stesso modo, l'uso di un percorso hardcoded per gli assembly .NET Framework, l'esecuzione di un confronto delle uguaglianze con una particolare versione di .NET Framework e l'acquisizione del valore di un campo privato tramite reflection non sono pratiche compatibili con le versioni precedenti. Inoltre, ogni versione di .NET Framework include correzioni di bug e modifiche correlate alla sicurezza che possono incidere sulla compatibilità di alcune app e componenti.

Se l'app o il componente non funziona come previsto in .NET Framework 4.5 (e versioni intermedie: .NET Framework 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 o 4.8), usare gli elenchi di controllo seguenti:

- Se l'app è stata sviluppata per l'esecuzione in qualsiasi versione di .NET Framework a partire da .NET Framework 4.0, vedere [Compatibilità delle](application-compatibility.md) applicazioni per generare elenchi di modifiche tra la versione di .NET Framework di destinazione e la versione in cui è in esecuzione l'app.

- Se si dispone di un'app .NET Framework 3.5, vedere anche [Problemi di migrazione di .NET Framework 4](../migration-guide/net-framework-4-migration-issues.md).

- Se si dispone di un'app .NET Framework 2.0, vedere anche [Modifiche in .NET Framework 3.5 SP1](https://docs.microsoft.com/previous-versions/dotnet/articles/dd310284(v=msdn.10)).

- Se si dispone di un'app .NET Framework 1.1, vedere anche [Modifiche in .NET Framework 2.0](https://docs.microsoft.com/previous-versions/aa570326(v=msdn.10)).

- Se si sta eseguendo la ricompilazione del codice sorgente esistente per l'esecuzione in .NET Framework 4.5 o nelle relative versioni intermedie oppure si sta sviluppando una nuova versione di un'app o di un componente destinato a .NET Framework 4.5 o alle relative versioni intermedie da una codebase sorgente esistente, vedere [Elementi obsoleti nella libreria di classi .NET Framework](../whats-new/whats-obsolete.md) per i tipi e i membri obsoleti e applicare la soluzione alternativa descritta. (Il codice compilato precedentemente continuerà a essere in esecuzione sui tipi e i membri contrassegnati come obsoleti).

- Se si determina che una modifica in .NET Framework 4.5 ha interrotto l'app, vedere [Schema delle impostazioni di runtime](../configure-apps/file-schema/runtime/index.md) e in particolare l'[elemento \<AppContextSwitchOverrides>](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) per stabilire se è possibile usare un'impostazione di runtime nel file di configurazione dell'app per ripristinare il comportamento precedente.

- Se si verifica un problema non documentato, segnalarlo nel [sito della community degli sviluppatori .NET](https://developercommunity.visualstudio.com/spaces/61/index.html) oppure nel [repository GitHub Microsoft/dotnet](https://github.com/microsoft/dotnet/issues).

## <a name="side-by-side-execution"></a>Esecuzione side-by-side

Se non è possibile trovare una soluzione appropriata per il problema, tenere presente che .NET Framework 4.5 (o una delle sue versioni puntuali) viene eseguito affiancato alle versioni 1.1, 2.0 e 3.5 ed è un aggiornamento sul posto che sostituisce la versione 4. Per le app destinate alle versioni 1.1, 2.0 e 3.5, è possibile installare la versione appropriata di .NET Framework nel computer di destinazione per eseguire l'app nel proprio ambiente migliore. Per altre informazioni sull'esecuzione side-by-side, vedere [Esecuzione side-by-side](../deployment/side-by-side-execution.md).

## <a name="see-also"></a>Vedere anche

- [Novità](../whats-new/index.md)
- [Elementi obsoleti nella libreria di classi](../whats-new/whats-obsolete.md)
- [Compatibilità delle applicazioni](../migration-guide/application-compatibility.md)
- [Politica di supporto ufficiale di .NET Framework](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework)
- [Problemi di migrazione di .NET Framework 4](../migration-guide/net-framework-4-migration-issues.md)
