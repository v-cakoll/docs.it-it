---
title: Considerazioni sulla sicurezza degli assembly
description: Quando si compila un assembly .NET, è possibile specificare le autorizzazioni necessarie per l'esecuzione dell'assembly. Questo articolo illustra gli assembly con nome sicuro e gli strumenti di firma.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], security
- signcodes
- names [.NET Framework], assemblies
- strong-named assemblies, security considerations
- signing assemblies
- assemblies [.NET Framework], signing
- granting permissions, assemblies
- assemblies [.NET Framework], strong-named
- names [.NET Framework], strong names
- permissions [.NET Framework], assemblies
- security [.NET Framework], assemblies
- integrity with assemblies
ms.assetid: 1b5439c1-f3d5-4529-bd69-01814703d067
ms.openlocfilehash: 7f897241b121cf1bd52d02ee5f487aeafafc3cb0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378653"
---
# <a name="assembly-security-considerations"></a>Considerazioni sulla sicurezza degli assembly
Quando si compila un assembly, è possibile specificare l'insieme di autorizzazioni che verranno richieste per consentirne l'esecuzione. Se sussistano o meno le autorizzazioni per l'utilizzo di un assembly lo si evince dalle evidenze.  
  
 Le evidenze vengono utilizzate in due modi diversi:  
  
- L'evidenza di input viene unita all'evidenza acquisita durante il caricamento per creare un set di evidenze finale utilizzato per la risoluzione dei criteri. I metodi in cui viene usata tale semantica sono **Assembly.Load**, **Assembly.LoadFrom** e **Activator.CreateInstance**.  
  
- L'evidenza di input viene utilizzata non modificata come set di evidenze finale per la risoluzione dei criteri. I metodi in cui viene usata tale semantica sono **Assembly.Load(byte[])** e **AppDomain.DefineDynamicAssembly()**.  
  
  Autorizzazioni facoltative possono essere concesse dai [criteri di sicurezza](../../framework/misc/code-access-security-basics.md) impostati per il computer che eseguirà l'assembly. Se si desidera che il proprio codice gestisca tutte le possibili eccezioni di sicurezza, si può procedere in uno dei modi seguenti:  
  
- Inserire una richiesta per tutte le autorizzazioni di cui il codice deve disporre e gestire gli errori che si verificheranno in fase di caricamento nel caso in cui le autorizzazioni non venissero riconosciute.  
  
- Non prevedere una richiesta per le autorizzazioni eventualmente necessarie, ma limitarsi a predisporre la gestione delle eccezioni di sicurezza che si verificheranno in mancanza di tali autorizzazioni.  
  
  > [!NOTE]
  > Quello della sicurezza è un tema complesso in cui è possibile scegliere tra molte possibili opzioni. Per altre informazioni, vedere [Concetti principali sulla sicurezza](../../standard/security/key-security-concepts.md).  
  
 In fase di caricamento, l'evidenza dell'assembly viene utilizzata come input per i criteri di sicurezza. I criteri di sicurezza vengono stabiliti dall'azienda e dall'amministratore dei computer, così come dalle impostazioni adottate dallo stesso utente, e determinano l'insieme di autorizzazioni concesse a tutto il codice gestito che viene eseguito sul computer. È possibile stabilire criteri di sicurezza basati sull'autore dell'assembly (se questo dispone di una firma generata da uno strumento firma digitale), sul sito Web e la zona (come è definita in Internet Explorer) da cui è stato effettuato il download dell'assembly o sul nome sicuro dell'assembly. L'amministratore di un computer può ad esempio stabilire criteri di sicurezza che consentono a tutto il codice scaricato da un sito Web e firmato da una determinata azienda di software di accedere al database presente su un computer, ma non di scrivere sul disco rigido.  
  
## <a name="strong-named-assemblies-and-signing-tools"></a>Assembly con nome sicuro e strumenti per la firma  

 > [!WARNING]
 > Non usare i nomi sicuri per la sicurezza, poiché forniscono solo un'identità univoca.

 È possibile firmare un assembly in due modi diversi ma complementari: con un nome sicuro o tramite [SignTool.exe (strumento per la firma)](../../framework/tools/signtool-exe.md). La firma di un assembly con un nome sicuro comporta l'aggiunta della crittografia con chiave pubblica al file che contiene il manifesto dell'assembly. La firma con nome sicuro garantisce l'univocità del nome, ne impedisce l'utilizzo fraudolento e fornisce un'identità al chiamante quando un riferimento viene risolto.  
  
 I nomi sicuri non garantiscono alcun livello di attendibilità. A ciò provvede infatti [SignTool.exe (strumento per la firma)](../../framework/tools/signtool-exe.md). I due strumenti firma digitale impongono all'autore di provare la propria identità a un'autorità terza per ottenere un certificato. Il certificato viene poi incorporato nel file e può essere utilizzato da un amministratore per decidere se considerare attendibile l'autenticità del codice.  
  
 È possibile associare a un assembly il solo nome sicuro, la sola firma digitale creata tramite [SignTool.exe (strumento per la firma)](../../framework/tools/signtool-exe.md) o entrambi. Con i due strumenti firma digitale è possibile firmare un solo file alla volta. Nel caso di assembly su più file, si firmerà solo il file che contiene il manifesto dell'assembly. Il nome sicuro viene memorizzato nel file che contiene il manifesto dell'assembly, mentre la firma creata tramite [SignTool.exe (strumento per la firma)](../../framework/tools/signtool-exe.md) viene memorizzata in un'area riservata del file eseguibile portabile (PE, Portable Executable) che contiene il manifesto dell'assembly. La firma di un assembly realizzata tramite [SignTool.exe (strumento per la firma)](../../framework/tools/signtool-exe.md) può essere adottata (con o senza un nome sicuro) quando si ha già una gerarchia attendibile basata su firme generate tramite [SignTool.exe (strumento per la firma)](../../framework/tools/signtool-exe.md) o quando i propri criteri si avvalgono solo della chiave e non controllano la catena di attendibilità.  
  
> [!NOTE]
> Quando a un assembly si assegna sia un nome sicuro che una firma digitale, il nome sicuro deve essere assegnato per primo.  
  
 Common Language Runtime esegue anche una verifica hash. Il manifesto dell'assembly contiene infatti un elenco di tutti i file che compongono l'assembly, comprensivo dell'hash generato per ciascun file al momento della compilazione del manifesto. Quando si carica un file, viene calcolato il codice hash del relativo contenuto e viene eseguito un confronto con il valore hash archiviato nel manifesto. Se i due hash non corrispondono, l'assembly non viene caricato.  
  
 Poiché nomi sicuri e firme create tramite [SignTool.exe (strumento per la firma)](../../framework/tools/signtool-exe.md) garantiscono l'integrità, è possibile basare i criteri di sicurezza dall'accesso di codice su queste due evidenze degli assembly. I nomi sicuri e le firme create attraverso [SignTool.exe (strumento per la firma)](../../framework/tools/signtool-exe.md) garantiscono l'integrità tramite firme digitali e certificati. Tutte le tecnologie menzionate (verifica hash, denominazioni sicure e firme create mediante [SignTool.exe (strumento per la firma)](../../framework/tools/signtool-exe.md)) contribuiscono a garantire che l'assembly non sia stato alterato in alcun modo.  
  
## <a name="see-also"></a>Vedere anche

- [Assembly con nomi sicuri](strong-named.md)
- [Assembly in .NET](index.md)
- [SignTool. exe (strumento per la firma)](../../framework/tools/signtool-exe.md)
