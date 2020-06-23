---
title: 'Procedura: Individuare assembly usando DEVPATH'
description: Verificare che un assembly condiviso funzioni correttamente con molte applicazioni in .NET utilizzando un file di configurazione del computer XML e la variabile di ambiente DEVPATH.
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 50b61eedddabd660b1834565a61738f460ae9ff9
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105382"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>Procedura: Individuare assembly usando DEVPATH
Gli sviluppatori potrebbero voler assicurarsi che un assembly condiviso che compilano funzioni correttamente con più applicazioni. Anziché inserire continuamente l'assembly nel Global Assembly Cache durante il ciclo di sviluppo, lo sviluppatore può creare una variabile di ambiente DEVPATH che punti alla directory di output di compilazione per l'assembly.  
  
 Si supponga, ad esempio, che si stia compilando un assembly condiviso denominato MySharedAssembly e che la directory di output sia C:\MySharedAssembly\Debug. È possibile inserire C:\MySharedAssembly\Debug nella variabile DEVPATH. È quindi necessario specificare l' [\<developmentMode>](./file-schema/runtime/developmentmode-element.md) elemento nel file di configurazione del computer. Questo elemento indica al Common Language Runtime di utilizzare DEVPATH per individuare gli assembly.  
  
 L'assembly condiviso deve essere individuabile dal runtime.  Per specificare una directory privata per la risoluzione dei riferimenti ad assembly, utilizzare l' [ \<codeBase> elemento](./file-schema/runtime/codebase-element.md) o l' [ \<probing> elemento](./file-schema/runtime/probing-element.md) in un file di configurazione, come descritto in [specifica della posizione di un assembly](specify-assembly-location.md).  È anche possibile inserire l'assembly in una sottodirectory della directory dell'applicazione. Per altre informazioni, vedere [Modalità di individuazione di assembly del runtime](../deployment/how-the-runtime-locates-assemblies.md).  
  
> [!NOTE]
> Si tratta di una funzionalità avanzata, destinata solo allo sviluppo.  
  
 Nell'esempio seguente viene illustrato come fare in modo che il runtime cerchi gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.  
  
## <a name="example"></a>Esempio  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 Per impostazione predefinita, questa impostazione è false.  
  
> [!NOTE]
> Usare questa impostazione solo in fase di sviluppo. Il runtime non controlla le versioni in assembly con nome sicuro presenti in DEVPATH. Usa semplicemente il primo assembly trovato.  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione delle app tramite file di configurazione](index.md)
