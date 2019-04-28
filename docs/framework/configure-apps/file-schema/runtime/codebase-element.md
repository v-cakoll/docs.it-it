---
title: <codeBase> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
ms.openlocfilehash: b5825efcc613689e73fb56b6695fe7c75ff09136
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674194"
---
# <a name="codebase-element"></a>\<codeBase > elemento

Specifica in cui common language runtime può trovare un assembly.

\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase>

## <a name="syntax"></a>Sintassi

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|`href`|Attributo obbligatorio.<br /><br /> Specifica l'URL in cui il runtime può trovare la versione dell'assembly specificata.|
|`version`|Attributo obbligatorio.<br /><br /> Specifica la versione dell'assembly che viene applicata la codebase. Il formato di un numero di versione assembly *revisione*.|

## <a name="version-attribute"></a>Attributo di versione

|Value|Descrizione|
|-----------|-----------------|
|I valori validi per ogni parte del numero di versione sono compresi tra 0 e 65535.|Non applicabile.|

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`buildproviders`|Definisce una raccolta di provider di compilazione utilizzati per compilare file di risorse personalizzati. Possono essere presenti più provider di compilazione.|
|`compilation`|Consente di configurare tutte le impostazioni di compilazione usato da ASP.NET.|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`System.web`|Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.|

## <a name="remarks"></a>Note

Per il runtime utilizzare la  **\<codeBase >** impostazione in un file di configurazione di computer o i file dei criteri editore, il file anche necessario reindirizzare la versione dell'assembly. File di configurazione dell'applicazione possono avere un'impostazione di base di codice senza eseguire il reindirizzamento alla versione dell'assembly. Dopo aver determinato la versione di assembly da usare, il runtime si applica l'impostazione di base di codice dal file che determina la versione. Se non viene specificata alcuna codebase, il runtime esegue il probe per l'assembly nel modo consueto.

Se l'assembly ha un nome sicuro, la codebase può trovarsi in un punto qualsiasi nella rete intranet locale o in Internet. Se l'assembly è un assembly privato, l'impostazione di base di codice deve essere un percorso relativo alla directory dell'applicazione.

Per gli assembly senza un nome sicuro, la versione viene ignorata e il caricatore Usa la prima occorrenza di \<codebase > all'interno di \<dependentAssembly >. Se è presente una voce nel file di configurazione dell'applicazione che reindirizza l'associazione a un altro assembly, il reindirizzamento avrà la precedenza anche se la versione dell'assembly non corrisponde alla richiesta di associazione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come specificare dove il runtime può trovare un assembly.

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly"
                              publicKeyToken="32ab4ba45e0a69a1"
                              culture="neutral" />
            <codeBase version="2.0.0.0"
                      href="http://www.litwareinc.com/myAssembly.dll"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Specifica della posizione di un assembly](../../../../../docs/framework/configure-apps/specify-assembly-location.md)
- [Come il runtime individua gli assembly](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
