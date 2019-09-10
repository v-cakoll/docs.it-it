---
title: Generazione di comandi SQL nel provider di esempio
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: a59f1fecf85d63208c3388204c962b5838902ba7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854313"
---
# <a name="sql-generation-in-the-sample-provider"></a>Generazione di comandi SQL nel provider di esempio
Il [provider di esempio Entity Framework](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) illustra i nuovi componenti dei provider di dati ADO.NET che supportano l'Entity Framework.  Viene usato con database SQL Server 2005 e viene implementato come wrapper per il provider di dati ADO.NET 2.0 System.Data.SqlClient.  
  
 Il modulo di generazione SQL del Provider di esempio che, ad eccezione del file DmlSqlGenerator.cssi, si trova al di sotto della cartella di generazione SQL, produce una sola istruzione SQL SELECT usando un oggetto DbQueryCommandTree di input.  
  
## <a name="in-this-section"></a>In questa sezione  
 Questa sezione presenta i seguenti argomenti:  
  
 [Architettura e progettazione](architecture-and-design.md)  
  
 [Procedura dettagliata: Generazione SQL](walkthrough-sql-generation.md)  
  
## <a name="see-also"></a>Vedere anche

- [Generazione SQL](sql-generation.md)
