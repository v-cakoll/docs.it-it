---
title: Integrazione di Common Language Runtime di SQL Server
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: 5f6c1dcccaddeadb65e6fc949960b0232d00ed81
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45568839"
---
# <a name="sql-server-common-language-runtime-integration"></a>Integrazione di Common Language Runtime di SQL Server
In SQL Server 2005 è stata introdotta l'integrazione del componente CLR di .NET Framework per Microsoft Windows. Questo significa che è possibile scrivere stored procedure, trigger, tipi definiti dall'utente, funzioni definite dall'utente, aggregati definiti dall'utente e funzioni con valori di tabella di flusso usando qualsiasi linguaggio di .NET Framework, inclusi Microsoft Visual Basic .NET e Microsoft Visual C#. Lo spazio dei nomi <xref:Microsoft.SqlServer.Server> contiene un set di nuove API (Application Programming Interface) che consente l'interazione del codice gestito con l'ambiente Microsoft SQL Server.  
  
 Questa sezione descrive le funzionalità e i comportamenti specifici dell'integrazione CLR di SQL Server, nonché le estensioni specifiche in-process di SQL Server per ADO.NET.  
  
 In questa sezione vengono fornite solo le informazioni di base per iniziare a programmare con l'integrazione CLR di SQL Server. Tali informazioni non sono da considerarsi esaustive. Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.  
  
 **Documentazione online di SQL Server**  
  
1.  [Concetti di programmazione integrazione di Common Language Runtime (CLR)](https://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a>In questa sezione  
 [Introduzione all'integrazione CLR in SQL Server](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 Viene fornita un'introduzione all'integrazione CLR di SQL Server. Vengono forniti collegamenti ad argomenti aggiuntivi.  
  
 [Funzioni definite dall'utente CLR](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 Viene descritto come implementare e usare i diversi tipi di funzioni CLR, ovvero le funzioni con valori di tabella, le funzioni scalari e le funzioni di aggregazione definite dall'utente.  
  
 [Tipi definiti dall'utente CLR](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 Viene descritto come implementare e usare i tipi CLR definiti dall'utente. Vengono forniti collegamenti ad argomenti aggiuntivi.  
  
 [Stored procedure CLR](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 Viene descritto come implementare e usare le stored procedure CLR. Vengono forniti collegamenti ad argomenti aggiuntivi.  
  
 [Trigger CLR](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 Viene descritto come implementare e usare i trigger CLR. Vengono forniti collegamenti ad argomenti aggiuntivi.  
  
 [Connessione di contesto](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 Viene descritta la connessione di contesto.  
  
 [Comportamento specifico in-process SQL Server di ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 Vengono descritte le estensioni specifiche in-process di SQL Server per ADO.NET e la connessione di contesto. Vengono forniti collegamenti ad argomenti aggiuntivi.  
  
## <a name="see-also"></a>Vedere anche  
 [SQL Server e ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [Creazione di oggetti di SQL Server 2005 nel codice gestito](https://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
