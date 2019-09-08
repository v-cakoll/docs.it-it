---
title: Utilizzo di comandi per modificare i dati
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: 34c73549f18cd4bebb8caf842b252828b7f0a185
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780568"
---
# <a name="using-commands-to-modify-data"></a>Utilizzo di comandi per modificare i dati
Con un provider di dati .NET Framework è possibile eseguire stored procedure o istruzioni DDL (Data Definition Language), ad esempio CREATE TABLE e ALTER COLUMN, per modificare lo schema di un database o di un catalogo. Questi comandi non restituiscono righe come query, quindi l'oggetto **Command** fornisce un **ExecuteNonQuery** per elaborarli.  
  
 Oltre a usare **ExecuteNonQuery** per modificare lo schema, è anche possibile usare questo metodo per elaborare istruzioni SQL che modificano i dati ma che non restituiscono righe, ad esempio INSERT, Update e DELETE.  
  
 Anche se le righe non vengono restituite dal metodo **ExecuteNonQuery** , i parametri di input e di output e i valori restituiti possono essere passati e restituiti tramite la raccolta **Parameters** dell'oggetto **Command** .  
  
## <a name="in-this-section"></a>In questa sezione  
 [Aggiornamento di dati in un'origine dati](updating-data-in-a-data-source.md)  
 Viene descritto come eseguire i comandi o le stored procedure che modificano i dati in un database.  
  
 [Esecuzione di operazioni di catalogo](performing-catalog-operations.md)  
 Viene descritto come eseguire i comandi per la modifica dello schema di database.  
  
## <a name="see-also"></a>Vedere anche

- [Recupero e modifica di dati in ADO.NET](retrieving-and-modifying-data.md)
- [Comandi e parametri](commands-and-parameters.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
