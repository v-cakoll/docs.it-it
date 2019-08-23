---
title: Oggetto My. WebServices (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: c887f9b7c5a41c0aa02016354c46d5507b103d25
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918172"
---
# <a name="mywebservices-object"></a>Oggetto My.WebServices
Fornisce le proprietà per la creazione e l'accesso a una singola istanza di ogni servizio Web XML a cui fa riferimento il progetto corrente.  
  
## <a name="remarks"></a>Note  
 L'oggetto `My.WebServices` fornisce un'istanza di ogni servizio Web a cui si fa riferimento nel progetto corrente. Ogni istanza viene creata su richiesta. È possibile accedere a questi servizi Web tramite le proprietà dell'oggetto `My.WebServices`. Il nome della proprietà è uguale al nome del servizio Web a cui la proprietà accede. Qualsiasi classe che eredita da <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> è un servizio Web. Per informazioni sull'aggiunta di servizi Web a un progetto, vedere [accesso ai servizi Web dell'applicazione](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 L' `My.WebServices` oggetto espone solo i servizi Web associati al progetto corrente. Non fornisce l'accesso ai servizi Web dichiarati in dll a cui si fa riferimento. Per accedere a un servizio Web fornito da una DLL, è necessario utilizzare il nome completo del servizio Web nel formato *dllname*.WebServiceName. Per ulteriori informazioni, vedere [accesso ai servizi Web dell'applicazione](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 L'oggetto e le relative proprietà non sono disponibili per le applicazioni Web.  
  
## <a name="properties"></a>Properties  
 Ogni proprietà dell' `My.WebServices` oggetto fornisce l'accesso a un'istanza di un servizio Web a cui fa riferimento il progetto corrente. Il nome della proprietà è uguale al nome del servizio Web a cui accede la proprietà e il tipo della proprietà è uguale al tipo del servizio Web.  
  
> [!NOTE]
> Se si verifica un conflitto di nomi, il nome della proprietà per accedere a un servizio Web è *RootNamespace*_*namespace*\_*ServiceName*. Si considerino, ad esempio, due `Service1`servizi Web denominati. Se uno di questi servizi si trova nello spazio dei `WindowsApplication1` nomi radice e nello `Namespace1`spazio dei nomi, si accederà a `My.WebServices.WindowsApplication1_Namespace1_Service1`tale servizio utilizzando.  
  
 Quando si accede per la `My.WebServices` prima volta a una delle proprietà dell'oggetto, viene creata una nuova istanza del servizio Web che viene archiviata. Gli accessi successivi di tale proprietà restituiscono l'istanza del servizio Web.  
  
 È possibile eliminare un servizio Web assegnando `Nothing` alla proprietà per il servizio Web. Il metodo `Nothing` di impostazione della proprietà viene assegnato al valore archiviato. Se si assegna un valore diverso `Nothing` da alla proprietà, il setter genera un' <xref:System.ArgumentException> eccezione.  
  
 È possibile verificare se una proprietà dell' `My.WebServices` oggetto archivia un'istanza del servizio Web utilizzando l' `Is` operatore OR `IsNot` . È possibile utilizzare gli operatori per verificare se il valore della proprietà è `Nothing`.  
  
> [!NOTE]
> In genere, `Is` l' `IsNot` operatore o deve leggere il valore della proprietà per eseguire il confronto. Tuttavia, se la proprietà è attualmente `Nothing`archiviata, la proprietà crea una nuova istanza del servizio Web e quindi restituisce tale istanza. Tuttavia, il compilatore Visual Basic considera le proprietà dell' `My.WebServices` oggetto in modo specifico e consente all' `Is` operatore OR `IsNot` di controllare lo stato della proprietà senza modificarne il valore.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene `FahrenheitToCelsius` chiamato il metodo `TemperatureConverter` del servizio Web XML e viene restituito il risultato.  
  
 [!code-vb[VbVbalrMyWebService#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWebService/VB/Form1.vb#1)]  
  
 Per il corretto funzionamento di questo esempio, il progetto deve fare riferimento a `Converter`un servizio Web denominato e il servizio Web `ConvertTemperature` deve esporre il metodo. Per ulteriori informazioni, vedere [accesso ai servizi Web dell'applicazione](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Questo codice non funziona in un progetto di applicazione Web.  
  
## <a name="requirements"></a>Requisiti  
  
### <a name="availability-by-project-type"></a>Disponibilità per tipo di progetto  
  
|Tipo di progetto|Disponibile|  
|---|---|  
|Applicazione Windows|**Sì**|  
|Libreria di classi|**Sì**|  
|Applicazione console|**Sì**|  
|Libreria di controlli Windows|**Sì**|  
|Libreria di controlli Web|**Sì**|  
|Servizio Windows|**Sì**|  
|Sito Web|No|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>
- <xref:System.ArgumentException>
- [Accesso ai servizi Web dell'applicazione](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
