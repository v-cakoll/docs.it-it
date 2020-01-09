---
title: Creazione di nomi sicuri e librerie .NET
description: Procedure consigliate per la creazione di nomi sicuri per le librerie .NET.
ms.date: 10/16/2018
ms.openlocfilehash: 0c2dba06413bc6435e3350bf6cc48f1b5882a261
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706426"
---
# <a name="strong-naming"></a>Denominazione sicura

La creazione di nomi sicuri si riferisce alla firma di un assembly con una chiave, per produrre un [assembly con nome sicuro](../assembly/strong-named.md). Quando un assembly ha un nome sicuro, viene creata un'identità univoca basata sul nome e sul numero di versione dell'assembly e ciò può aiutare a evitare i conflitti di assembly.

Lo svantaggio dei nomi sicuri è che .NET Framework in Windows abilita il caricamento in modalità strict per gli assembly con nome sicuro. Un riferimento a un assembly con nome sicuro deve corrispondere esattamente alla versione a cui viene fatto riferimento da un assembly, quindi gli sviluppatori devono [configurare reindirizzamenti di binding](../../framework/configure-apps/redirect-assembly-versions.md) quando l'assembly viene usato:

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly" publicKeyToken="32ab4ba45e0a69a1" culture="neutral" />
            <bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

Quando gli sviluppatori .NET si lamentano dei nomi sicuri, in realtà ciò che non apprezzano è il caricamento degli assembly in modalità strict. Fortunatamente, questo problema riguarda solo .NET Framework. .NET Core, Xamarin, la piattaforma UWP e la maggior parte delle altre implementazioni .NET non prevedono il caricamento degli assembly in modalità strict, ovviando così al principale svantaggio dei nomi sicuri.

Un aspetto importante dei nomi sicuri è che sono virali: un assembly con nome sicuro può fare riferimento solo ad altri assembly con nome sicuro. Se la libreria non ha un nome sicuro, gli sviluppatori che stanno progettando un'applicazione o una libreria che richiede nomi sicuri non la potranno usare.

I vantaggi dei nomi sicuri sono i seguenti:

1. Altri assembly con nome sicuro possono fare riferimento all'assembly e usarlo.
2. L'assembly può essere archiviato nella Global Assembly Cache (GAC).
3. L'assembly può essere caricato affiancato ad altre versioni dell'assembly. Il caricamento dell'assembly affiancato è comunemente richiesto dalle applicazioni con architetture plug-in.

## <a name="create-strong-named-net-libraries"></a>Creare librerie .NET con nome sicuro

È consigliabile usare un nome sicuro per le librerie .NET open source. L'uso di un nome sicuro per un assembly garantisce che la maggior parte degli utenti possa usare l'assembly e il caricamento dell'assembly in modalità strict riguarda solo .NET Framework.

> [!NOTE]
> Queste linee guida sono specifiche per le librerie .NET distribuite pubblicamente, ad esempio le librerie .NET pubblicate in NuGet.org. Il nome sicuro non è richiesto dalla maggior parte delle applicazioni .NET e non deve essere eseguito per impostazione predefinita.

**✔️ VALUTARE** l'uso di nomi sicuri per gli assembly della libreria.

**✔️ VALUTARE** l'aggiunta della chiave per la creazione di nomi sicuri nel sistema di controllo del codice sorgente.

> Una chiave disponibile pubblicamente consente agli sviluppatori di modificare e ricompilare il codice sorgente della libreria con la stessa chiave.
> 
> Non rendere pubblica la chiave per la creazione di nomi sicuri se è stata usata in precedenza per concedere autorizzazioni speciali in [scenari di attendibilità parziale](../../framework/misc/using-libraries-from-partially-trusted-code.md). In caso contrario, si potrebbero compromettere gli ambienti esistenti.

> [!IMPORTANT]
> Quando si vuole indicare l'identità dell'editore del codice, usare [Authenticode](/windows-hardware/drivers/install/authenticode) e la [firma di pacchetti NuGet](/nuget/create-packages/sign-a-package). Non usare la sicurezza dall'accesso di codice come prevenzione per la sicurezza.

**✔️ VALUTARE** l'incremento della versione dell'assembly solo per le modifiche di versione principale, per aiutare gli utenti a ridurre i reindirizzamenti di binding e la frequenza di aggiornamento.

> Leggere altre informazioni su [controllo delle versioni e versione degli assembly](./versioning.md#assembly-version).

**❌** non aggiungere, rimuovere o modificare la chiave di denominazione sicura.

> Se si modifica una chiave per la creazione di nomi sicuri di un assembly, viene modificata l'identità dell'assembly e il codice compilato che lo usa non funziona più. Per altre informazioni, vedere [Binary breaking change](./breaking-changes.md#binary-breaking-change) (Modifica che causa un'interruzione del codice binario).

**❌** non pubblicare versioni con nome sicuro e senza nome sicuro della libreria. Ad esempio, `Contoso.Api` e `Contoso.Api.StrongNamed`.

> La pubblicazione di due pacchetti comporta la biforcazione dell'ecosistema di sviluppo. Se un'applicazione dipende da entrambi i pacchetti, inoltre, possono verificarsi conflitti di nomi di tipo. Per quanto riguarda .NET, si tratta di tipi diversi in assembly diversi.

>[!div class="step-by-step"]
>[Precedente](cross-platform-targeting.md)
>[Successivo](nuget.md)
