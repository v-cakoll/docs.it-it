---
title: Provider di servizi dati (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: a0160b1b-3d9c-4cc8-8391-cb0986a60a41
ms.openlocfilehash: e4f887ebf467c967b8b72c19deafed2c9759e4ed
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975346"
---
# <a name="data-services-providers-wcf-data-services"></a>Provider di servizi dati (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] supporta più modelli di provider per l'esposizione di dati come feed di Open Data Protocol (OData). In questo argomento vengono fornite le informazioni che consentono di scegliere il provider di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] più adatto all'origine dati usata.  
  
## <a name="data-source-providers"></a>Provider di origini dati  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] supporta i provider seguenti per la definizione del modello di dati di un servizio dati.  
  
|Provider|Descrizione|  
|--------------|-----------------|  
|Provider di Entity Framework|Questo provider usa ADO.NET Entity Framework per consentire l'uso di dati relazionali con un servizio dati mediante la definizione di un modello di dati che esegue il mapping ai dati relazionali. L'origine dati può essere SQL Server o qualsiasi altra origine dati con supporto di provider di terze parti per Entity Framework. È necessario usare il provider di Entity Framework quando si dispone di un'origine dati relazionale, ad esempio un database di SQL Server. Per ulteriori informazioni, vedere [Provider Entity Framework](entity-framework-provider-wcf-data-services.md).|  
|Provider di reflection|Questo provider usa la reflection per consentire la definizione di un modello di dati basato su classi di dati esistenti che possono essere esposte come istanze dell'interfaccia <xref:System.Linq.IQueryable%601>. Gli aggiornamenti vengono abilitati mediante l'implementazione dell'interfaccia <xref:System.Data.Services.IUpdatable>. È necessario usare questo provider quando si dispone di classi di dati statiche definite in fase di esecuzione, ad esempio quelle generate da LINQ to SQL o definite da un set di dati tipizzato. Per ulteriori informazioni, vedere [provider di Reflection](reflection-provider-wcf-data-services.md).|  
|Provider di servizi dati personalizzati|[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] include un set di provider che consentono di definire in modo dinamico un modello di dati basato su tipi di dati ad associazione tardiva. È necessario implementare queste interfacce quando i dati esposti non sono noti al momento della progettazione dell'applicazione o quando il provider di reflection o il provider di Entity Framework non è sufficiente. Per ulteriori informazioni, vedere [provider di servizi dati personalizzati](custom-data-service-providers-wcf-data-services.md).|  
  
## <a name="other-data-service-providers"></a>Altri provider di servizi dati  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] dispone del provider di servizi dati aggiuntivo seguente che migliora le prestazioni di un'origine dati definita utilizzando uno degli altri provider.  
  
|Provider|Descrizione|  
|--------------|-----------------|  
|Provider di flusso|Questo provider consente di esporre tipi di dati per oggetti binari di grandi dimensioni tramite [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Un provider di flusso viene creato mediante l'implementazione dell'interfaccia <xref:System.Data.Services.Providers.IDataServiceStreamProvider>. È possibile implementare questo provider insieme a qualsiasi provider dell'origine dati. Per ulteriori informazioni, vedere [provider di flussi](streaming-provider-wcf-data-services.md).|  
  
## <a name="see-also"></a>Vedere anche

- [Definizione di WCF Data Services](defining-wcf-data-services.md)
- [Configurazione del servizio dati](configuring-the-data-service-wcf-data-services.md)
- [Hosting del servizio dati](hosting-the-data-service-wcf-data-services.md)
