---
title: Integrazione di Common Language Runtime di SQL Server
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: 77b40c6a1576b87d9bb4a7eb4b1ee3df8828b892
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780866"
---
# <a name="sql-server-common-language-runtime-integration"></a>Integrazione di Common Language Runtime di SQL Server
In SQL Server 2005 è stata introdotta l'integrazione del componente CLR di .NET Framework per Microsoft Windows. Questo significa che è possibile scrivere stored procedure, trigger, tipi definiti dall'utente, funzioni definite dall'utente, aggregati definiti dall'utente e funzioni con valori di tabella di flusso usando qualsiasi linguaggio di .NET Framework, inclusi Microsoft Visual Basic .NET e Microsoft Visual C#. Lo spazio dei nomi <xref:Microsoft.SqlServer.Server> contiene un set di nuove API (Application Programming Interface) che consente l'interazione del codice gestito con l'ambiente Microsoft SQL Server.  
  
 Questa sezione descrive le funzionalità e i comportamenti specifici dell'integrazione CLR di SQL Server, nonché le estensioni specifiche in-process di SQL Server per ADO.NET.  
  
 In questa sezione vengono fornite solo le informazioni di base per iniziare a programmare con l'integrazione CLR di SQL Server. Tali informazioni non sono da considerarsi esaustive. Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.  
  
 **Documentazione online di SQL Server**  
  
1. [Concetti relativi alla programmazione dell'integrazione con CLR (Common Language Runtime)](https://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a>In questa sezione  
 [Introduzione all'integrazione CLR in SQL Server](introduction-to-sql-server-clr-integration.md)  
 Viene fornita un'introduzione all'integrazione CLR di SQL Server. Vengono forniti collegamenti ad argomenti aggiuntivi.  
  
 [Funzioni definite dall'utente CLR](clr-user-defined-functions.md)  
 Viene descritto come implementare e usare i diversi tipi di funzioni CLR, ovvero le funzioni con valori di tabella, le funzioni scalari e le funzioni di aggregazione definite dall'utente.  
  
 [Tipi definiti dall'utente CLR](clr-user-defined-types.md)  
 Viene descritto come implementare e usare i tipi CLR definiti dall'utente. Vengono forniti collegamenti ad argomenti aggiuntivi.  
  
 [Stored procedure CLR](clr-stored-procedures.md)  
 Viene descritto come implementare e usare le stored procedure CLR. Vengono forniti collegamenti ad argomenti aggiuntivi.  
  
 [Trigger CLR](clr-triggers.md)  
 Viene descritto come implementare e usare i trigger CLR. Vengono forniti collegamenti ad argomenti aggiuntivi.  
  
 [Connessione di contesto](the-context-connection.md)  
 Viene descritta la connessione di contesto.  
  
 [Comportamento specifico in-process SQL Server di ADO.NET](sql-server-in-process-specific-behavior-of-adonet.md)  
 Vengono descritte le estensioni specifiche in-process di SQL Server per ADO.NET e la connessione di contesto. Vengono forniti collegamenti ad argomenti aggiuntivi.  
  
## <a name="see-also"></a>Vedere anche

- [SQL Server e ADO.NET](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
