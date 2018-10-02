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
ms.openlocfilehash: 3a9ae9c60ad7de80d04f16984b3b2fb048421cc2
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48037326"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>Procedura: individuare assembly mediante DEVPATH
Gli sviluppatori desiderano assicurarsi che funzioni correttamente un assembly condiviso in corso di sviluppo con più applicazioni. Anziché inserire continuamente l'assembly nella global assembly cache durante il ciclo di sviluppo, lo sviluppatore può creare una variabile di ambiente DEVPATH che punta alla directory di output di compilazione per l'assembly.  
  
 Ad esempio, si supponga che si sta creando un assembly condiviso denominato MySharedAssembly e la directory di output è C:\MySharedAssembly\Debug. È possibile inserire C:\MySharedAssembly\Debug nella variabile DEVPATH. È quindi necessario specificare il [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) elemento nel file di configurazione del computer. Questo elemento indica a common language runtime da usare DEVPATH per individuare gli assembly.  
  
 L'assembly condiviso deve essere individuabile dal runtime.  Per specificare una cartella privata per la risoluzione dei riferimenti agli assembly, utilizzare il [ \<codeBase > elemento](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) oppure [ \<probing > elemento](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in un file di configurazione, come descritto in [Che specifica la posizione dell'Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md).  È anche possibile inserire l'assembly in una sottodirectory della directory dell'applicazione. Per altre informazioni, vedere [Modalità di individuazione di assembly del runtime](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
> [!NOTE]
>  Si tratta di una funzionalità avanzata, destinata solo allo sviluppo.  
  
 Nell'esempio seguente viene illustrato come parte del runtime cercare gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.  
  
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
>  Usare questa impostazione solo in fase di sviluppo. Il runtime non verifica se le versioni di assembly con nome sicuro trovato nel DEVPATH. Utilizza semplicemente il primo assembly individuato.  
  
## <a name="see-also"></a>Vedere anche  
 [Configurazione delle app .NET Framework](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
