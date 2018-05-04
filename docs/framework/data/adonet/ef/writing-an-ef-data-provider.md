---
title: Scrittura di un provider di dati Entity Framework
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 578de94aa191d7302b762f1cdc87d4a6810037e3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="writing-an-entity-framework-data-provider"></a>Scrittura di un provider di dati Entity Framework
In questa sezione viene descritto come scrivere un [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider per supportare un'origine dati diverso da SQL Server. Il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] include un provider che supporta SQL Server.  
  
## <a name="introducing-the-entity-framework-provider-model"></a>Introduzione al modello di provider Entity Framework  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] è indipendente dal database ed è possibile scrivere un provider usando il modello di provider ADO.NET per connettersi a un set di origini dati differente.  
  
 Il provider di dati Entity Framework, compilato usando il modello di provider di dati ADO.NET, consente di eseguire le funzioni seguenti:  
  
-   Mapping dei tipi primitivi EDM (Entity Data Model) ai tipi di provider.  
  
-   Esposizione delle funzioni specifiche del provider.  
  
-   Generazione di comandi specifici del provider per un determinato DbQueryCommandTree per supportare le query [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
-   Generazione di comandi di aggiornamento specifici del provider per un determinato DbModificationCommandTree per supportare gli aggiornamenti mediante [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
-   Esposizione di file di mapping per la definizione dello schema di archiviazione per supportare la generazione di un modello basato su un database.  
  
-   Esposizione di metadati, ad esempio tabelle e visualizzazioni, mediante un modello concettuale.  
  
 ![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")  
  
## <a name="sample"></a>Esempio  
 Vedere la [Provider di esempio Entity Framework](http://go.microsoft.com/fwlink/?LinkId=180616) per un esempio di un [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider che supporta un'origine dati diverso da SQL Server.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Generazione SQL](../../../../../docs/framework/data/adonet/ef/sql-generation.md)  
  
 [Generazione di comandi SQL di modifica](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)  
  
 [Specifica del manifesto del provider](../../../../../docs/framework/data/adonet/ef/provider-manifest-specification.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di provider di dati](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)
