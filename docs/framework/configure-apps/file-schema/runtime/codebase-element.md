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
ms.openlocfilehash: 475b7df55ed509157c1da0aeb8f979de238c72b5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70971881"
---
# <a name="codebase-element"></a>\<codeBase> Elemento

Specifica la posizione in cui il Common Language Runtime può trovare un assembly.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<codeBase>**

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
|`href`|Attributo obbligatorio.<br /><br /> Specifica l'URL in cui il runtime è in grado di trovare la versione specificata dell'assembly.|
|`version`|Attributo obbligatorio.<br /><br /> Specifica la versione dell'assembly a cui si applica la codebase. Il formato di un numero di versione dell'assembly è *Major. minor. Build. Revision*.|

## <a name="version-attribute"></a>Attributo Version

|Valore|Description|
|-----------|-----------------|
|I valori validi per ogni parte del numero di versione sono compresi tra 0 e 65535.|Non applicabile.|

### <a name="child-elements"></a>Elementi figlio

No.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`buildproviders`|Definisce una raccolta di provider di compilazione utilizzati per compilare file di risorse personalizzati. Possono essere presenti più provider di compilazione.|
|`compilation`|Configura tutte le impostazioni di compilazione utilizzate da ASP.NET.|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`System.web`|Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.|

## <a name="remarks"></a>Commenti

Affinché il runtime usi l' **\<codeBase>** impostazione in un file di configurazione del computer o in un file dei criteri editore, il file deve anche reindirizzare la versione dell'assembly. I file di configurazione dell'applicazione possono avere un'impostazione codebase senza reindirizzamento della versione dell'assembly. Dopo aver determinato quale versione dell'assembly utilizzare, il runtime applica l'impostazione codebase dal file che determina la versione. Se non è indicata alcuna codebase, il runtime esegue il probe per l'assembly nel modo consueto.

Se l'assembly ha un nome sicuro, l'impostazione codebase può trovarsi in qualsiasi punto della rete Intranet locale o Internet. Se l'assembly è un assembly privato, l'impostazione codebase deve essere un percorso relativo alla directory dell'applicazione.

Per gli assembly senza nome sicuro, la versione viene ignorata e il caricatore usa il primo aspetto di \<codebase> all'interno di \<dependentAssembly> . Se nel file di configurazione dell'applicazione è presente una voce che reindirizza il binding a un altro assembly, il reindirizzamento avrà la precedenza anche se la versione dell'assembly non corrisponde alla richiesta di associazione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come specificare la posizione in cui il runtime può trovare un assembly.

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

## <a name="see-also"></a>Vedi anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- [Specificare la posizione di un assembly](../../../../standard/assembly/location.md)
- [Come il runtime individua gli assembly](../../../deployment/how-the-runtime-locates-assemblies.md)
