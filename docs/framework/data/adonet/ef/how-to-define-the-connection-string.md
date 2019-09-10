---
title: 'Procedura: Definire la stringa di connessione'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: a78158c7553c0b479b935e3b94931313df912c2f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854654"
---
# <a name="how-to-define-the-connection-string"></a>Procedura: Definire la stringa di connessione

In questo argomento viene illustrato come definire la stringa di connessione usata per la connessione a un modello concettuale. Questo argomento è basato sul modello concettuale [Sales di AdventureWorks](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) . Il modello Sales di AdventureWorks viene utilizzato in tutti gli argomenti correlati alle attività nella documentazione di Entity Framework. In questo argomento si presuppone che sia già stato configurato il Entity Framework e che sia stato definito il modello Sales di AdventureWorks. Per altre informazioni, vedere [Procedura: Definire manualmente i file](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))di modello e di mapping. Le procedure descritte in questo argomento sono incluse anche [in procedura: Configurare manualmente un progetto](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))di Entity Framework.

> [!NOTE]
> Se si usa la procedura guidata Entity Data Model in un progetto di Visual Studio, viene generato automaticamente un file con estensione edmx e il progetto viene configurato per l'uso del Entity Framework. Per altre informazioni, vedere [Procedura: Utilizzare la procedura guidata Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))

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

Se il progetto non dispone di un file di configurazione dell'applicazione, è possibile aggiungerne uno scegliendo **Aggiungi nuovo elemento** dal menu **progetto** , selezionando la categoria **generale** , selezionando **file di configurazione dell'applicazione**e quindi facendo clic su **Aggiungi**.

## <a name="see-also"></a>Vedere anche

- [Guida rapida](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))
- [Procedura: Creare un nuovo file con estensione edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))
- [Strumenti di ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
