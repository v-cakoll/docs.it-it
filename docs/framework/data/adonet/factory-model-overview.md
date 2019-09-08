---
title: Cenni preliminari sul modello di factory
ms.date: 03/30/2017
ms.assetid: b5dc81c4-7554-44b9-b513-769bd61e2e7b
ms.openlocfilehash: 7d50ddd3b02b66a5b2be41eaba5cf9a497b5f1b3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795083"
---
# <a name="factory-model-overview"></a>Cenni preliminari sul modello di factory
In ADO.NET 2.0 sono state introdotte nuove classi di base nello spazio dei nomi <xref:System.Data.Common>. Le classi di base sono astratte, ovvero non è possibile creare un'istanza di tali classi in modo diretto. Includono <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand>e <xref:System.Data.Common.DbDataAdapter> e sono condivise tra i provider di dati .NET Framework, ad esempio <xref:System.Data.SqlClient> e <xref:System.Data.OleDb>. L'aggiunta di classi di base consente di aggiungere più facilmente funzionalità ai provider di dati .NET Framework senza dover creare nuove interfacce.  
  
 In ADO.NET 2.0 sono state inoltre introdotte classi di base astratte che consentono agli sviluppatori di scrivere codice per l'accesso ai dati generico e non dipendente da un provider di dati specifico.  
  
## <a name="the-factory-design-pattern"></a>Modello di progettazione a livello di factory  
 Il modello di programmazione per la scrittura di codice indipendente dal provider è basato sul modello di progettazione a livello di factory, che usa una singola API per accedere ai database di più provider. Il nome di questo modello è appropriato in quanto richiede l'uso di un oggetto specializzato soltanto per creare altri oggetti, non molto diversamente da una fabbrica reale. Per una descrizione più dettagliata dello schema di progettazione della Factory, vedere [scrittura di codice di accesso ai dati generico in ASP.NET 2,0 e ADO.NET 2,0](https://go.microsoft.com/fwlink/?LinkId=55915).
  
 A partire da ADO.NET 2.0 la classe <xref:System.Data.Common.DbProviderFactories> fornisce metodi `static` (o `Shared` in Visual Basic) per la creazione di un'istanza di <xref:System.Data.Common.DbProviderFactory>. L'istanza restituisce quindi un oggetto fortemente tipizzato corretto basato sulle informazioni fornite dal provider e dalla stringa di connessione in fase di esecuzione.  
  
## <a name="see-also"></a>Vedere anche

- [Recupero di una classe DbProviderFactory](obtaining-a-dbproviderfactory.md)
- [DbConnection, DbCommand e DbException](dbconnection-dbcommand-and-dbexception.md)
- [Modifica di dati con un oggetto DbDataAdapter](modifying-data-with-a-dbdataadapter.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
