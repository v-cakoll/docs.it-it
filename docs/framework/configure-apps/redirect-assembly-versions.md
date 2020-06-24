---
title: Reindirizzamento delle versioni di assembly
description: Reindirizza i riferimenti di associazione in fase di compilazione a versioni diverse di assembly .NET, assembly di terze parti o assembly dell'app.
ms.date: 03/30/2017
helpviewer_keywords:
- assembly binding, redirection
- redirecting assembly binding to earlier version
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], binding redirection
ms.assetid: 88fb1a17-6ac9-4b57-8028-193aec1f727c
ms.openlocfilehash: 4cfd4336fb9999c996bea28eb86f1143932d4c51
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141734"
---
# <a name="redirecting-assembly-versions"></a>Reindirizzamento delle versioni di assembly

È possibile reindirizzare i riferimenti delle associazioni in fase di compilazione agli assembly di .NET Framework, di terze parti o specifici dell'app. È possibile reindirizzare l'app per l'uso di una diversa versione di un assembly in diversi modi: con i criteri editore, tramite un file di configurazione dell'app o mediante il file di configurazione del computer. In questo articolo viene illustrato il funzionamento dell'associazione di assembly in .NET Framework e come può essere configurato.

<a name="BKMK_Assemblyunificationanddefaultbinding"></a>
## <a name="assembly-unification-and-default-binding"></a>Unificazione e associazione predefinita degli assembly
 Le associazioni agli assembly .NET Framework vengono talvolta reindirizzate mediante un processo denominato *unificazione degli assembly*. .NET Framework è costituito da una versione di Common Language Runtime e da oltre venti assembly .NET Framework che costituiscono la libreria dei tipi. Questi assembly .NET Framework vengono gestiti dal runtime come una singola unità. Per impostazione predefinita, quando viene avviata un'app, tutti i riferimenti ai tipi nel codice eseguito dal runtime vengono indirizzati agli assembly .NET Framework che hanno lo stesso numero di versione del runtime caricato in un processo. I reindirizzamenti eseguiti con questo modello rappresentano il comportamento predefinito per il runtime.

 Ad esempio, se l'app fa riferimento ai tipi nello spazio dei nomi System.XML ed è stata compilata usando il .NET Framework 4,5, contiene riferimenti statici all'assembly System.XML fornito con la versione di runtime 4,5. Per reindirizzare il riferimento dell'associazione in modo da puntare all'assembly System.XML fornito con .NET Framework 4, si possono inserire le informazioni di reindirizzamento nel file di configurazione dell'app. Il reindirizzamento di un'associazione in un file di configurazione per un assembly .NET Framework unificato determina l'annullamento dell'unificazione per tale assembly.

 Inoltre, è possibile reindirizzare manualmente l'associazione di assembly per gli assembly di terze parti in caso di più versioni disponibili.

<a name="BKMK_Redirectingassemblyversionsbyusingpublisherpolicy"></a>
## <a name="redirecting-assembly-versions-by-using-publisher-policy"></a>Reindirizzamento delle versioni di assembly mediante i criteri editore
 I fornitori di assembly possono dirigere le app verso una versione più recente di un assembly fornendo un file dei criteri editore con l'assembly aggiornato. Il file dei criteri editore si trova nella Global Assembly Cache e contiene le impostazioni per il reindirizzamento degli assembly.

 Ogni versione *principale*.*secondaria* di un assembly è dotata del relativo file dei criteri editore. Ad esempio, le impostazioni di reindirizzamento dalla versione 2.0.2.222 alla 2.0.3.000 e dalla 2.0.2.321 alla 2.0.3.000 sono contenute nello stesso file, poiché sono associate alla versione 2.0. Tuttavia, un reindirizzamento dalla versione 3.0.0.999 alla versione 4.0.0.000 va inserito nel file per la versione 3.0.999. Ogni versione principale di .NET Framework è dotata del relativo file dei criteri editore.

 Se è disponibile un file dei criteri editore per un assembly, il runtime controlla tale file dopo aver controllato il manifesto dell'assembly e i file di configurazione dell'app. I fornitori usano i file dei criteri editore solo se il nuovo assembly è compatibile con la versione precedente dell'assembly reindirizzato.

 È possibile ignorare i criteri editore per l'app specificando le impostazioni nel file di configurazione dell'app, come illustrato nella sezione [Esclusione dei criteri editore](#bypass_PP).

<a name="BKMK_Redirectingassemblyversionsattheapplevel"></a>
## <a name="redirecting-assembly-versions-at-the-app-level"></a>Reindirizzamento delle versioni di assembly a livello di app
 Esistono alcune tecniche differenti per modificare il comportamento di associazione per l'app dal file di configurazione dell'app: è possibile modificare manualmente il file, basarsi sul reindirizzamento dell'associazione automatico oppure specificare il comportamento di associazione ignorando i criteri editore.

### <a name="manually-editing-the-app-config-file"></a>Modifica manuale del file di configurazione di un'app
 È possibile modificare manualmente il file di configurazione di un'app per risolvere i problemi dell'assembly. Ad esempio, se un fornitore rilascia una versione più recente di un assembly usato dall'app senza fornire i criteri dell'editore, poiché tramite essi non viene garantita la compatibilità con le versioni precedenti, l'app può essere configurata in modo da usare la versione più recente dell'assembly inserendo informazioni di associazione dell'assembly nel file di configurazione dell'app come riportato di seguito.

```xml
<dependentAssembly>
  <assemblyIdentity name="someAssembly"
    publicKeyToken="32ab4ba45e0a69a1"
    culture="en-us" />
  <bindingRedirect oldVersion="7.0.0.0" newVersion="8.0.0.0" />
</dependentAssembly>
```

### <a name="relying-on-automatic-binding-redirection"></a>Reindirizzamento di associazione automatico

Quando si crea un'app desktop in Visual Studio destinata a .NET Framework 4.5.1 o versione successiva, l'app usa il reindirizzamento di associazione automatico. Ciò significa che se due componenti fanno riferimento a versioni diverse dello stesso assembly con nome sicuro, il runtime aggiunge automaticamente un reindirizzamento di associazione alla versione più recente dell'assembly nel file di output di configurazione dell'app (app.config). Il reindirizzamento esegue l'override dell'unificazione di assembly che in caso contrario potrebbe essere eseguito. Il file app.config di origine non viene modificato. Si supponga, ad esempio, che l'app faccia riferimento direttamente a un componente di .NET Framework fuori banda, ma viene usata una libreria di terze parti destinata a una versione precedente dello stesso componente. Quando si compila l'app, il file di configurazione dell'app di output viene modificato in modo da contenere un reindirizzamento di associazione alla versione più recente del componente. Se si crea un'app Web, si riceve un avviso di compilazione relativo al conflitto di associazione, che a sua volta offre la possibilità di aggiungere il reindirizzamento di associazione necessario al file di configurazione Web di origine.

Se si aggiungono manualmente reindirizzamenti di binding al file di app.config di origine, in fase di compilazione, Visual Studio tenterà di unificare gli assembly in base ai reindirizzamenti di binding aggiunti. Ad esempio, si inserisce il seguente reindirizzamento dell'associazione per un assembly:

`<bindingRedirect oldVersion="3.0.0.0" newVersion="2.0.0.0" />`

Se un altro progetto nell'app fa riferimento alla versione 1.0.0.0 dello stesso assembly, tramite il reindirizzamento di associazione automatico viene aggiunta la seguente voce al file app.config di output in modo da unificare l'app nella versione 2.0.0.0 di questo assembly:

`<bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0" />`

È possibile abilitare il reindirizzamento di associazione automatico se l'app è destinata alle versioni precedenti del .NET Framework. È possibile eseguire l'override di questo comportamento predefinito fornendo le informazioni di reindirizzamento dell'associazione nel file di app.config per qualsiasi assembly o disattivando la funzionalità di reindirizzamento di associazione. Per informazioni su come attivare o disattivare questa funzionalità, vedere [procedura: abilitare e disabilitare il reindirizzamento di associazione automatico](how-to-enable-and-disable-automatic-binding-redirection.md).

<a name="bypass_PP"></a>
### <a name="bypassing-publisher-policy"></a>Esclusione dei criteri editore
 È possibile eseguire l'override dei criteri editore nel file di configurazione dell'app, se necessario. Ad esempio, le nuove versioni degli assembly, anche se si presentano come compatibili con le versioni precedenti, possono causare problemi per l'esecuzione di un'app. Se si vuole ignorare i criteri dell'editore, aggiungere un [\<publisherPolicy>](./file-schema/runtime/publisherpolicy-element.md) elemento all' [\<dependentAssembly>](./file-schema/runtime/dependentassembly-element.md) elemento nel file di configurazione dell'app e impostare l'attributo **Apply** su **No**, che sostituisce le impostazioni **Yes** precedenti.

 `<publisherPolicy apply="no" />`

 Ignorare quindi i criteri editore per garantire agli utenti il corretto funzionamento dell'app, ma assicurarsi di notificare il problema al fornitore dell'assembly. Se per un assembly è disponibile il file sui criteri editore, il fornitore deve assicurare la compatibilità dell'assembly con le versioni precedenti e garantire il corretto funzionamento della nuova versione per i client.

<a name="BKMK_Redirectingassemblyversionsatthemachinelevel"></a>
## <a name="redirecting-assembly-versions-at-the-machine-level"></a>Reindirizzamento delle versioni di assembly a livello di computer
 In rari casi, è possibile che l'amministratore del computer desideri impostare tutte le app installate in un computer affinché usino una determinata versione di un assembly. Ad esempio, l'amministratore potrebbe voler usare una particolare versione dell'assembly in tutte le app, perché tale versione è in grado di risolvere un problema di sicurezza. Se un assembly viene reindirizzato in un file di configurazione di un computer, tutte le app presenti sul computer che usano la versione precedente saranno indirizzate all'uso della nuova versione. Il file di configurazione del computer esegue l'override del file di configurazione dell'app e del file dei criteri editore. Questo file si trova nella directory %*percorso installazione runtime*%\Config. In genere, .NET Framework è installato nella directory %drive%\Windows\Microsoft.NET\Framework.

<a name="BKMK_Specifyingassemblybindinginconfigurationfiles"></a>
## <a name="specifying-assembly-binding-in-configuration-files"></a>Specifica dell'associazione di assembly nei file di configurazione
 Si usa lo stesso formato XML per specificare i reindirizzamenti delle associazioni, indipendentemente dal fatto che venga usato il file di configurazione dell'app, il file di configurazione del computer o il file dei criteri editore. Per reindirizzare una versione dell'assembly a un'altra, usare l' [\<bindingRedirect>](./file-schema/runtime/bindingredirect-element.md) elemento. L'attributo **oldVersion** può specificare una singola versione di assembly oppure un insieme di versioni. L'attributo `newVersion` deve specificare una singola versione.  Se si imposta `<bindingRedirect oldVersion="1.1.0.0-1.2.0.0" newVersion="2.0.0.0"/>` , ad esempio, il runtime userà la versione 2.0.0.0 anziché una versione di assembly compresa tra 1.1.0.0 e 1.2.0.0.

 Nell'esempio di codice seguente viene illustrata una varietà di scenari di reindirizzamento dell'associazione. L'esempio specifica un reindirizzamento per un intervallo delle versioni per `myAssembly`e un singolo reindirizzamento dell'associazione per `mySecondAssembly`. L'esempio specifica inoltre che il file dei criteri editore non esegue l'override di reindirizzamenti delle associazioni per `myThirdAssembly`.

 Per associare un assembly, è necessario specificare la stringa "urn: schemas-microsoft-com: ASM. V1" con l'attributo **xmlns** nel [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) tag.

```xml
<configuration>
  <runtime>
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
      <dependentAssembly>
        <assemblyIdentity name="myAssembly"
          publicKeyToken="32ab4ba45e0a69a1"
          culture="en-us" />
        <!-- Assembly versions can be redirected in app,
          publisher policy, or machine configuration files. -->
        <bindingRedirect oldVersion="1.0.0.0-2.0.0.0" newVersion="3.0.0.0" />
      </dependentAssembly>
      <dependentAssembly>
        <assemblyIdentity name="mySecondAssembly"
          publicKeyToken="32ab4ba45e0a69a1"
          culture="en-us" />
             <bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0" />
      </dependentAssembly>
      <dependentAssembly>
      <assemblyIdentity name="myThirdAssembly"
        publicKeyToken="32ab4ba45e0a69a1"
        culture="en-us" />
        <!-- Publisher policy can be set only in the app
          configuration file. -->
        <publisherPolicy apply="no" />
      </dependentAssembly>
    </assemblyBinding>
  </runtime>
</configuration>
```

### <a name="limiting-assembly--bindings-to-a-specific-version"></a>Limitazione delle associazioni di assembly a una versione specifica
 È possibile usare l'attributo **appliesTo** [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) nell'elemento in un file di configurazione dell'applicazione per reindirizzare i riferimenti di associazione di assembly a una versione specifica del .NET Framework. Questo attributo facoltativo usa un numero di versione di .NET Framework per indicare la versione a cui deve essere applicato. Se non è specificato alcun attributo **appliesTo** , l' [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) elemento si applica a tutte le versioni del .NET Framework.

 Per reindirizzare l'associazione di assembly per un assembly .NET Framework 3.5, ad esempio, verrà incluso il codice XML riportato di seguito nel file di configurazione dell'app.

```xml
<runtime>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1"
    appliesTo="v3.5">
    <dependentAssembly>
      <!-- assembly information goes here -->
    </dependentAssembly>
  </assemblyBinding>
</runtime>
```

 È necessario fornire le informazioni di reindirizzamento nell'ordine della versione. Ad esempio, immettere le informazioni di reindirizzamento dell'associazione dell'assembly per gli assembly .NET Framework 3.5 seguiti dagli assembly .NET Framework 4.5. Immettere infine le informazioni di reindirizzamento dell'binding di assembly per qualsiasi reindirizzamento di assembly .NET Framework in cui non viene usato l'attributo **appliesTo** e che quindi viene applicato a tutte le versioni di .NET Framework. In caso di conflitto nel reindirizzamento, verrà usata la prima istruzione di reindirizzamento corrispondente nel file di configurazione.

 Per reindirizzare, ad esempio, un riferimento a un assembly di .NET Framework 3.5 e un altro riferimento a un assembly di .NET Framework 4, usare il modello illustrato nel frammento di codice che segue.

```xml
<assemblyBinding xmlns="..." appliesTo="v3.5 ">
  <!--.NET Framework version 3.5 redirects here -->
</assemblyBinding>

<assemblyBinding xmlns="..." appliesTo="v4.0.30319">
  <!--.NET Framework version 4.0 redirects here -->
</assemblyBinding>

<assemblyBinding xmlns="...">
  <!-- redirects meant for all versions of the runtime -->
</assemblyBinding>
```

## <a name="see-also"></a>Vedere anche

- [Procedura: Abilitare e disabilitare il reindirizzamento di associazione automatico](how-to-enable-and-disable-automatic-binding-redirection.md)
- [\<bindingRedirect>Elemento](./file-schema/runtime/bindingredirect-element.md)
- [Autorizzazione di sicurezza per il reindirizzamento delle versioni di assembly](assembly-binding-redirection-security-permission.md)
- [Assembly in .NET](../../standard/assembly/index.md)
- [Programmazione con gli assembly](../../standard/assembly/index.md)
- [Modalità di individuazione degli assembly da parte del runtime](../deployment/how-the-runtime-locates-assemblies.md)
- [Configurazione di applicazioni](index.md)
- [Schema delle impostazioni di runtime](./file-schema/runtime/index.md)
- [Schema del file di configurazione](./file-schema/index.md)
- [Procedura: Creare criteri editore](how-to-create-a-publisher-policy.md)
