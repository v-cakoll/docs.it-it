---
title: Specifica della posizione di un assembly
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: ead69d1e850050214c15295134c06ff6f66e9760
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646028"
---
# <a name="specifying-an-assemblys-location"></a>Specifica della posizione di un assembly
Esistono due modi per specificare la posizione di un assieme:  
  
- Utilizzo dell'elemento [ \<codeBase>.](./file-schema/runtime/codebase-element.md)  
  
- Utilizzo dell'elemento [ \<>sondaggio.](./file-schema/runtime/probing-element.md)  
  
 È inoltre possibile utilizzare [lo strumento .NET Framework Configuration (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) per specificare i percorsi degli assembly o i percorsi per Common Language Runtime di eseguire il probe degli assembly.  
  
## <a name="using-the-codebase-element"></a>Utilizzo \<dell'elemento codeBase>  
 È possibile utilizzare l'elemento ** \<codeBase>** solo nella configurazione del computer o nei file dei criteri dell'editore che reindirizzano anche la versione dell'assembly. Quando il runtime determina la versione dell'assembly da utilizzare, applica l'impostazione della base di codice dal file che determina la versione. Se non viene indicata alcuna base di codice, il runtime esegue il probe per l'assembly in modo normale. Per informazioni [dettagliate,](../deployment/how-the-runtime-locates-assemblies.md)vedere Come il runtime individua gli assembly .  
  
 Nell'esempio seguente viene illustrato come specificare il percorso di un assembly.  
  
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
  
 L'attributo **version** è obbligatorio per tutti gli assembly con nome sicuro, ma deve essere omesso per gli assembly che non sono con nome sicuro. L'elemento ** \<codeBase>** richiede l'attributo **href.** Non è possibile specificare intervalli di versioni nell'elemento ** \<codeBase>.**  
  
> [!NOTE]
> Se si fornisce un suggerimento di base di codice per un assembly senza nome sicuro, l'hint deve puntare alla base dell'applicazione o a una sottodirectory della directory di base dell'applicazione.  
  
## <a name="using-the-probing-element"></a>Utilizzo \<dell'elemento> sondaggioUsing the sbing> Element  
 Il runtime individua gli assembly che non dispongono di una base di codice tramite sondaggio. Per ulteriori informazioni sul sondaggio, vedere [Come il runtime individua gli assembly](../deployment/how-the-runtime-locates-assemblies.md).  
  
 È possibile utilizzare l'elemento [ \<>sondaggio](./file-schema/runtime/probing-element.md) nel file di configurazione dell'applicazione per specificare le sottodirectory in cui il runtime deve eseguire la ricerca durante l'individuazione di un assembly. Nell'esempio seguente viene illustrato come specificare le directory in cui il runtime deve eseguire la ricerca.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 L'attributo **privatePath** contiene le directory in cui il runtime deve cercare gli assembly. Se l'applicazione si trova nel percorso C:, Programmi, MyApp, il runtime cercherà gli assembly che non specificano una base di codice in C:. Le directory specificate in **privatePath** devono essere sottodirectory della directory di base dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Assembly in .NET](../../standard/assembly/index.md)
- [Programmazione con gli assembly](../../standard/assembly/index.md)
- [Come il runtime individua gli assembly](../deployment/how-the-runtime-locates-assemblies.md)
- [Configurazione delle app tramite file di configurazione](index.md)
