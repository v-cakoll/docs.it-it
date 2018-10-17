---
title: Denominazione sicura e le librerie .NET
description: Le procedure consigliate per sicuro delle librerie .NET di denominazione.
author: jamesnk
ms.author: mairaw
ms.date: 10/16/2018
ms.openlocfilehash: e3f7d443eb9acc84c800ea2611b803733085391c
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49372806"
---
# <a name="strong-naming"></a>Denominazione sicura

Denominazione sicura fa riferimento a firmare un assembly con una chiave, producendo un [assembly con nome sicuro](../../framework/app-domains/strong-named-assemblies.md). Quando un assembly è sicuro, crea un'identità univoca in base al numero di versione nome e l'assembly e può aiutare a evitare i conflitti di assembly.

Lo svantaggio di nome sicuro è che .NET Framework su Windows consente strict durante il caricamento degli assembly dopo che un assembly ha un nome sicuro. Un riferimento di assembly con nome sicuro debba corrispondere esattamente alla versione fa riferimento un assembly, imporre agli sviluppatori [configurare i reindirizzamenti di associazione](../../framework/configure-apps/redirect-assembly-versions.md) quando si usa l'assembly:

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

Quando gli sviluppatori .NET si lamentano nome sicuro, cosa è in genere reclamo è il caricamento dell'assembly strict. Fortunatamente, questo problema è isolata e prevede di .NET Framework. La maggior parte delle altre implementazioni di .NET, Xamarin, UWP e .NET core non è il caricamento dell'assembly strict e rimuove lo svantaggio principale di nome sicuro.

Un aspetto importante del nome sicuro è costituito da virale: un nome sicuro assembly possono fare riferimento solo altri sicuro degli assembly con nome. Se la libreria non è sicura denominato, è stato escluso gli sviluppatori che stanno progettando un'applicazione o una raccolta che è necessario un nome sicuro dal loro utilizzo.

Sono i vantaggi del nome sicuro:

1. L'assembly può essere fatto riferimento e usato da altri assembly con nome sicuro.
2. L'assembly può essere archiviato nella Global Assembly Cache (GAC).
3. L'assembly può essere caricato affiancato con altre versioni dell'assembly. Il caricamento dell'assembly side-by-side è comunemente richieste dalle applicazioni con architetture di plug-in.

## <a name="create-strong-named-net-libraries"></a>Creare sicuro denominato librerie .NET

È necessario un nome sicuro le librerie .NET open source. Un assembly di denominazione sicura garantisce la maggior parte degli utenti può usarla e solo il caricamento dell'assembly strict influisce su .NET Framework.

> [!NOTE]
> Questo materiale sussidiario è specifico di librerie .NET distribuite pubblicamente, ad esempio le librerie .NET pubblicati su NuGet.org. Nome sicuro non richiesti dalla maggior parte delle applicazioni .NET e non deve essere eseguita per impostazione predefinita.

**Provare a ✔️** sicuro gli assembly della libreria.

**Provare a ✔️** archiviare la chiave utilizzata per nome sicuro nel sistema di controllo di origine.

> Una chiave disponibile pubblicamente consente agli sviluppatori di modificare e ricompilare il codice sorgente della libreria con la stessa chiave.

> [!IMPORTANT]
> Quando un'identità del servizio di crittografia, è possibile definire [Authenticode](/windows-hardware/drivers/install/authenticode) e [firmare il pacchetto NuGet](/nuget/create-packages/sign-a-package) sono consigliati. Nome sicuro di non usare per motivi di sicurezza.

**Provare a ✔️** incrementare la versione dell'assembly sulle modifiche di versione principale solo per consentire agli utenti di ridurre i reindirizzamenti di associazione e con quale frequenza vengono aggiornati.

> Altre informazioni, vedere [controllo delle versioni e la versione dell'assembly](./versioning.md#assembly-version).

**NON ❌** aggiungere, rimuovere o modificare la chiave di denominazione intenso.

> Modifica della chiave di denominazione sicuro di un assembly viene modificato l'identità dell'assembly e interrompe il codice compilato che lo utilizza. Per altre informazioni, vedere [binario modifiche di rilievo](./breaking-changes.md#binary-breaking-change).

**NON ❌** pubblicare versioni sicuro e non nome sicuro della libreria. Ad esempio, `Contoso.Api` e `Contoso.Api.StrongNamed`.

> Pubblicazione due fork di pacchetti per gli sviluppatori eco-sistema. Inoltre, se un'applicazione finisce in entrambi i pacchetti base lo sviluppatore può verificarsi conflitti di nomi di tipo. Per quanto riguarda .NET sono diversi tipi in assembly diversi.

>[!div class="step-by-step"]
[Precedente](./cross-platform-targeting.md)
[Successivo](./nuget.md)
