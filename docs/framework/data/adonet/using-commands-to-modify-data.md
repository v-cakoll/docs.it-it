---
title: Utilizzo di comandi per modificare i dati
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: 6388eecb2e96970f47383b61985d672bd0419a1e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43773428"
---
# <a name="using-commands-to-modify-data"></a>Utilizzo di comandi per modificare i dati
Con un provider di dati .NET Framework è possibile eseguire stored procedure o istruzioni DDL (Data Definition Language), ad esempio CREATE TABLE e ALTER COLUMN, per modificare lo schema di un database o di un catalogo. Questi comandi non restituiscono righe come farebbe una query, in modo che il **comandi** oggetto fornisce un' **ExecuteNonQuery** per elaborarli.  
  
 Oltre a usare **ExecuteNonQuery** per modificare lo schema, è anche possibile usare questo metodo per elaborare istruzioni SQL che modificano i dati ma che non restituiscono righe, ad esempio INSERT, UPDATE e DELETE.  
  
 Anche se non viene restituita alcuna riga dal **ExecuteNonQuery** i parametri di metodo di input e output e valori restituiti possono essere passati e restituiti tramite il **parametri** raccolta del **comando**  oggetto.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Aggiornamento di dati in un'origine dati](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 Viene descritto come eseguire i comandi o le stored procedure che modificano i dati in un database.  
  
 [Esecuzione di operazioni di catalogo](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 Viene descritto come eseguire i comandi per la modifica dello schema di database.  
  
## <a name="see-also"></a>Vedere anche  
 [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Comandi e parametri](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
