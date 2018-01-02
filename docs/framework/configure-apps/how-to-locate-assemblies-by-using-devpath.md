---
title: 'Procedura: individuare assembly mediante DEVPATH'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 4ee4200a67ef9d9d123be3bc32b02ac61512d23b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
 [Configurazione delle app .NET Framework](http://msdn.microsoft.com/en-us/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
