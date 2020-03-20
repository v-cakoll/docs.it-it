---
title: 'Procedura: definire una stringa di connessione'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: e5b675a50f883825cce97275048447b79b64cc97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150571"
---
# <a name="how-to-define-the-connection-string"></a>Procedura: definire una stringa di connessione

In questo argomento viene illustrato come definire la stringa di connessione usata per la connessione a un modello concettuale. Questo argomento è basato sul modello concettuale [AdventureWorks Sales.](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) Il modello Sales di AdventureWorks viene utilizzato in tutti gli argomenti correlati alle attività nella documentazione di Entity Framework. In questo argomento si presuppone che Entity Framework sia già stato configurato e definito il modello Sales di AdventureWorks. Per ulteriori informazioni, vedere [Procedura: definire manualmente il modello e i file](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))di mapping . Le procedure descritte in questo argomento sono incluse anche in [Procedura: Configurare manualmente un progetto Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).

> [!NOTE]
> Se si utilizza la procedura guidata Entity Data Model in un progetto di Visual Studio, viene generato automaticamente un file con estensione edmx e il progetto viene configurato per l'utilizzo di Entity Framework. Per ulteriori informazioni, vedere [Procedura: utilizzare la procedura guidata Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).

## <a name="to-define-the-entity-framework-connection-string"></a>Per definire la stringa di connessione Entity Framework

- Aprire il file di configurazione dell'applicazione (app.config) del progetto e aggiungere la stringa di connessione seguente.

```xml
<connectionStrings>
    <add name="AdventureWorksEntities"
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

Se il progetto non dispone di un file di configurazione dell'applicazione, è possibile aggiungerne uno scegliendo **Aggiungi nuovo elemento** dal menu **Progetto** , selezionando la categoria **Generale** , selezionando File di **configurazione dell'applicazione**, quindi facendo clic su **Aggiungi**.

## <a name="see-also"></a>Vedere anche

- [Quickstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))
- [Procedura: creare un nuovo file con estensione edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))
- [Strumenti di ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
