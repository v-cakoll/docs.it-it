---
title: Specifica della posizione di un assembly
description: Vedere come specificare il percorso di un assembly in .NET usando l'elemento codebase o l'elemento probe in un file di configurazione XML.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: e14bdc12598d0aa6cdd2789b09a04ab8ed134169
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141704"
---
# <a name="specifying-an-assemblys-location"></a>Specifica della posizione di un assembly
È possibile specificare la posizione di un assembly in due modi:  
  
- Utilizzando l' [\<codeBase>](./file-schema/runtime/codebase-element.md) elemento.  
  
- Utilizzando l' [\<probing>](./file-schema/runtime/probing-element.md) elemento.  
  
 È anche possibile usare lo [strumento di configurazione .NET Framework (Mscorcfg. msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) per specificare i percorsi degli assembly o specificare i percorsi per il Common Language Runtime per eseguire il probe degli assembly.  
  
## <a name="using-the-codebase-element"></a>Utilizzo dell' \<codeBase> elemento  
 È possibile usare l' **\<codeBase>** elemento solo nei file di configurazione del computer o dei criteri dell'editore che reindirizzano anche la versione dell'assembly. Quando il runtime determina la versione dell'assembly da usare, applica l'impostazione codebase dal file che determina la versione. Se non è indicata alcuna codebase, il runtime esegue il probe per l'assembly in modo normale. Per informazioni dettagliate, vedere [come il runtime individua gli assembly](../deployment/how-the-runtime-locates-assemblies.md).  
  
 Nell'esempio seguente viene illustrato come specificare la posizione di un assembly.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 L'attributo **Version** è obbligatorio per tutti gli assembly con nome sicuro, ma deve essere omesso per gli assembly con nome sicuro. L' **\<codeBase>** elemento richiede l'attributo **href** . Non è possibile specificare gli intervalli di versione nell' **\<codeBase>** elemento.  
  
> [!NOTE]
> Se si fornisce un hint codebase per un assembly senza nome sicuro, l'hint deve puntare alla base dell'applicazione o a una sottodirectory della directory di base dell'applicazione.  
  
## <a name="using-the-probing-element"></a>Utilizzo dell' \<probing> elemento  
 Il runtime individua gli assembly che non dispongono di una codebase tramite sondaggio. Per altre informazioni sul sondaggio, vedere [come il runtime individua gli assembly](../deployment/how-the-runtime-locates-assemblies.md).  
  
 È possibile utilizzare l' [\<probing>](./file-schema/runtime/probing-element.md) elemento nel file di configurazione dell'applicazione per specificare le sottodirectory in cui il runtime deve eseguire la ricerca durante l'individuazione di un assembly. Nell'esempio seguente viene illustrato come specificare le directory in cui eseguire la ricerca del runtime.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 L'attributo **privatePath** contiene le directory che il runtime deve cercare per gli assembly. Se l'applicazione si trova in C:\Program C:\Programmi\MyApp, il runtime cercherà gli assembly che non specificano una codebase in C:\Program C:\Programmi\MyApp\Bin, C:\Program C:\Programmi\MyApp\Bin2\Subbin e C:\Program C:\Programmi\MyApp\Bin3. Le directory specificate in **privatePath** devono essere sottodirectory della directory di base dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Assembly in .NET](../../standard/assembly/index.md)
- [Programmazione con gli assembly](../../standard/assembly/index.md)
- [Modalità di individuazione degli assembly da parte del runtime](../deployment/how-the-runtime-locates-assemblies.md)
- [Configurazione delle app tramite file di configurazione](index.md)
