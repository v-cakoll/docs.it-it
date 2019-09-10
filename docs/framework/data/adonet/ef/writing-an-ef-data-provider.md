---
title: Scrittura di un provider di dati Entity Framework
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 29aa8cb1c6b31d9ada6b01860d76bcf03d37416c
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854156"
---
# <a name="writing-an-entity-framework-data-provider"></a>Scrittura di un provider di dati Entity Framework
In questa sezione viene illustrato come scrivere un provider Entity Framework per supportare un'origine dati diversa da SQL Server. Il Entity Framework include un provider che supporta SQL Server.  
  
## <a name="introducing-the-entity-framework-provider-model"></a>Introduzione al modello di provider Entity Framework  
 Il Entity Framework è indipendente dal database ed è possibile scrivere un provider utilizzando il modello di provider ADO.NET per connettersi a un set diversificato di origini dati.  
  
 Il provider di dati Entity Framework, compilato usando il modello di provider di dati ADO.NET, consente di eseguire le funzioni seguenti:  
  
- Mapping dei tipi primitivi EDM (Entity Data Model) ai tipi di provider.  
  
- Esposizione delle funzioni specifiche del provider.  
  
- Genera comandi specifici del provider per un determinato DbQueryCommandTree per supportare le query Entity Framework.  
  
- Genera comandi di aggiornamento specifici del provider per un determinato DbModificationCommandTree per supportare gli aggiornamenti tramite il Entity Framework.  
  
- Esposizione di file di mapping per la definizione dello schema di archiviazione per supportare la generazione di un modello basato su un database.  
  
- Esposizione di metadati, ad esempio tabelle e visualizzazioni, mediante un modello concettuale.  
  
 ![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")  
  
## <a name="sample"></a>Esempio  
 Vedere il [provider di esempio Entity Framework](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) per un esempio di un provider Entity Framework che supporta un'origine dati diversa da SQL Server.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Generazione SQL](sql-generation.md)  
  
 [Generazione di comandi SQL di modifica](modification-sql-generation.md)  
  
 [Specifica del manifesto del provider](provider-manifest-specification.md)  
  
## <a name="see-also"></a>Vedere anche

- [Uso di provider di dati](working-with-data-providers.md)
