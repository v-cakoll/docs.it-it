---
title: Considerazioni sulla distribuzione (Entity Framework)
ms.date: 03/30/2017
ms.assetid: 3a847a22-4eb8-4565-b18b-453bbca070db
ms.openlocfilehash: 4456a466a7b76c68b3185bf586494f8591440844
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761259"
---
# <a name="deployment-considerations-entity-framework"></a>Considerazioni sulla distribuzione (Entity Framework)
In questo argomento vengono fornite informazioni sulla distribuzione di applicazioni che usano ADO.NET Entity Framework per l'accesso ai dati. Per ulteriori informazioni su Entity Framework, vedere [Introduzione](../../../../../docs/framework/data/adonet/ef/getting-started.md).  
  
 Entity Framework fornisce un set di strumenti che si integrano con Visual Studio e semplificano le attività di sviluppo in questo ambiente. Per ulteriori informazioni, vedere [ADO.NET Entity Data Model Tools](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527). In questo argomento non viene descritto come usare le tecnologie specifiche per distribuire un'applicazione basata su Entity Framework.  
  
 Visual Studio include strumenti per la distribuzione di applicazioni, ad esempio ClickOnce. Per ulteriori informazioni, vedere [distribuzione di applicazioni e componenti](/visualstudio/deployment/deploying-applications-services-and-components) nella documentazione di Visual Studio.  
  
 Le considerazioni seguenti riguardano la distribuzione di un'applicazione che usa Entity Framework:  
  
-   Entity Framework è un componente di .NET Framework a partire da .NET Framework 3.5 Service Pack 1 (SP1). Quando si distribuisce un'applicazione basata su Entity Framework, è necessario verificare che sia installato .NET Framework 3.5 SP1 o una versione successiva.  
  
-   Quando viene generato un modello concettuale tramite la procedura guidata Entity Data Model, nel file di configurazione dell'applicazione viene creata una stringa di connessione. I file di modello e di mapping possono essere incorporati come risorse dell'applicazione oppure essere copiati nella directory di output. Per impostazione predefinita, questi file vengono distribuiti come risorse dell'applicazione incorporate. Usare la proprietà `Metadata Artifact Processing` del file di Entity Designer per selezionare una di queste opzioni. Per ulteriori informazioni, vedere [procedura: copiare file di modello e Mapping alla Directory di Output](http://msdn.microsoft.com/library/e2c9820f-1705-457e-9fdb-8b289f3179b4).  
  
-   Assicurarsi che le informazioni sul modello e sul mapping (espresse in Conceptual Schema Definition Language (CSDL), Store Schema Definition Language (SSDL) e Mapping Specification Language (MSL)) vengano distribuite insieme all'applicazione e nella posizione specificata dalla stringa di connessione. Per altre informazioni, vedere [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md) (Stringhe di connessione).  
  
-   Quando si incorporano informazioni sul modello e sul mapping come risorse dell'applicazione, è necessario ricompilare e ridistribuire l'applicazione ogni volta che il modello concettuale viene aggiornato.  
  
-   Poiché Entity Framework è un componente di .NET Framework, può essere ridistribuito con l'applicazione, come consentito dal contratto di licenza di .NET Framework.  
  
## <a name="see-also"></a>Vedere anche  
 [ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)  
 [Considerazioni sullo sviluppo e sulla distribuzione](../../../../../docs/framework/data/adonet/ef/development-and-deployment-considerations.md)
