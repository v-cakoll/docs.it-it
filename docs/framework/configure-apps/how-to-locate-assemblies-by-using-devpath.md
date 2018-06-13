---
title: 'Procedura: individuare assembly mediante DEVPATH'
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 918acf069c63d3aa8187f0f04e1f6c55ec961458
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755461"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>Procedura: individuare assembly mediante DEVPATH
Gli sviluppatori desiderano assicurarsi che funzioni correttamente in un assembly condiviso che viene compilato con più applicazioni. Anziché inserire continuamente l'assembly nella global assembly cache durante il ciclo di sviluppo, lo sviluppatore può creare una variabile di ambiente DEVPATH che punta alla directory di output di compilazione per l'assembly.  
  
 Ad esempio, si supponga che si compila un assembly condiviso denominato MySharedAssembly e la directory di output è C:\MySharedAssembly\Debug. È possibile inserire C:\MySharedAssembly\Debug nella variabile DEVPATH. È quindi necessario specificare il [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) elemento nel file di configurazione del computer. Questo elemento indica a common language runtime utilizza la variabile DEVPATH per individuare gli assembly.  
  
 L'assembly condiviso deve essere individuabile dal runtime.  Per specificare una cartella privata per la risoluzione dei riferimenti agli assembly, utilizzare il [ \<codeBase > elemento](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) o [ \<probing > elemento](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in un file di configurazione, come descritto in [Specificando il percorso di un Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md).  È anche possibile inserire l'assembly in una sottodirectory della directory dell'applicazione. Per altre informazioni, vedere [Modalità di individuazione di assembly del runtime](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
> [!NOTE]
>  Si tratta di una funzionalità avanzata, destinata solo allo sviluppo.  
  
 Nell'esempio seguente viene illustrato come impostare il runtime cercare gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.  
  
## <a name="example"></a>Esempio  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 L'impostazione predefinita è false.  
  
> [!NOTE]
>  Utilizzare questa impostazione solo in fase di sviluppo. Il runtime non controllate le versioni degli assembly con nome sicuro, vedere il DEVPATH. Usa semplicemente il primo assembly individuato.  
  
## <a name="see-also"></a>Vedere anche  
 [Configurazione di App .NET Framework](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
