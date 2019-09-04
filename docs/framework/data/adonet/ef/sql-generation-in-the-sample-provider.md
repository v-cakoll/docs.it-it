---
title: Generazione di comandi SQL nel provider di esempio
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: d0e058cdc4dd3f7a1a04ab6eea5acf4d3deabb89
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248503"
---
# <a name="sql-generation-in-the-sample-provider"></a>Generazione di comandi SQL nel provider di esempio
Il [provider di esempio Entity Framework](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) illustra i nuovi componenti dei provider di dati ADO.NET che [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]supportano.  Viene usato con database SQL Server 2005 e viene implementato come wrapper per il provider di dati ADO.NET 2.0 System.Data.SqlClient.  
  
 Il modulo di generazione SQL del Provider di esempio che, ad eccezione del file DmlSqlGenerator.cssi, si trova al di sotto della cartella di generazione SQL, produce una sola istruzione SQL SELECT usando un oggetto DbQueryCommandTree di input.  
  
## <a name="in-this-section"></a>In questa sezione  
 Questa sezione presenta i seguenti argomenti:  
  
 [Architettura e progettazione](architecture-and-design.md)  
  
 [Procedura dettagliata: Generazione SQL](walkthrough-sql-generation.md)  
  
## <a name="see-also"></a>Vedere anche

- [Generazione SQL](sql-generation.md)
