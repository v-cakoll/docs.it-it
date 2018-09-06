---
title: Oggetto My. WebServices (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: 7ae99bec5797591e53c6c77f5d9f88589352104c
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43862396"
---
# <a name="mywebservices-object"></a>Oggetto My.WebServices
Fornisce le proprietà per la creazione e l'accesso a una singola istanza di ogni servizio Web XML a cui fanno riferimento al progetto corrente.  
  
## <a name="remarks"></a>Note  
 L'oggetto `My.WebServices` fornisce un'istanza di ogni servizio Web a cui si fa riferimento nel progetto corrente. Ogni istanza viene creata su richiesta. È possibile accedere a questi servizi Web tramite le proprietà dell'oggetto `My.WebServices`. Il nome della proprietà è uguale al nome del servizio Web a cui la proprietà accede. Qualsiasi classe che eredita da <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> è un servizio Web. Per informazioni sull'aggiunta di servizi Web a un progetto, vedere [l'accesso ai servizi Web dell'applicazione](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Il `My.WebServices` oggetto espone solo i servizi Web associati al progetto corrente. Non fornisce accesso ai servizi Web dichiarati nelle DLL di cui viene fatto riferimento. Per accedere a un servizio Web che fornisce una DLL, è necessario usare il nome completo del servizio Web, nel formato *DllName*. *WebServiceName*. Per altre informazioni, vedere [l'accesso ai servizi Web dell'applicazione](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 L'oggetto e le relative proprietà non sono disponibili per le applicazioni Web.  
  
## <a name="properties"></a>Proprietà  
 Ogni proprietà del `My.WebServices` oggetto consente di accedere a un'istanza di un servizio Web a cui fanno riferimento al progetto corrente. Il nome della proprietà è identico al nome del servizio Web che accede a proprietà e il tipo della proprietà è identico al tipo del servizio Web.  
  
> [!NOTE]
>  Se si verifica un conflitto di nomi, il nome della proprietà per l'accesso a un servizio Web viene *RootNamespace*_*Namespace*\_*ServiceName*. Si consideri ad esempio due servizi Web denominati `Service1`. Se uno di questi servizi è nello spazio dei nomi radice `WindowsApplication1` e nello spazio dei nomi `Namespace1`, si accederà a tale servizio utilizzando `My.WebServices.WindowsApplication1_Namespace1_Service1`.  
  
 Quando si accede a uno del `My.WebServices` proprietà dell'oggetto, crea una nuova istanza del servizio Web e lo archivia. Gli accessi successivi di tale proprietà restituiscono quell'istanza del servizio Web.  
  
 È possibile eliminare un servizio Web tramite l'assegnazione di `Nothing` alla proprietà per il servizio Web. Assegna i setter delle proprietà `Nothing` al valore archiviato. Se si assegna un valore qualsiasi diverso da `Nothing` alla proprietà setter genera un <xref:System.ArgumentException> eccezione.  
  
 È possibile verificare se una proprietà del `My.WebServices` oggetto archivia un'istanza del servizio Web usando il `Is` o `IsNot` operatore. È possibile usare tali operatori per verificare se il valore della proprietà è `Nothing`.  
  
> [!NOTE]
>  In genere, il `Is` o `IsNot` operatore ha leggere il valore della proprietà per eseguire il confronto. Tuttavia, se la proprietà attualmente Archivia `Nothing`, la proprietà crea una nuova istanza del servizio Web e quindi restituisce tale istanza. Tuttavia, il compilatore Visual Basic considera le proprietà del `My.WebServices` dell'oggetto in modo specifico e consente la `Is` o `IsNot` operatore per controllare lo stato della proprietà senza modificarne il valore.  
  
## <a name="example"></a>Esempio  
 Questo esempio chiama il `FahrenheitToCelsius` metodo del `TemperatureConverter` servizio Web XML e restituisce il risultato.  
  
 [!code-vb[VbVbalrMyWebService#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-webservices-object_1.vb)]  
  
 Per questo esempio funzioni, il progetto deve fare riferimento a un servizio Web denominato `Converter`, e tale servizio Web deve esporre il `ConvertTemperature` (metodo). Per altre informazioni, vedere [l'accesso ai servizi Web dell'applicazione](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Questo codice non funziona in un progetto di applicazione Web.  
  
## <a name="requirements"></a>Requisiti  
  
### <a name="availability-by-project-type"></a>Disponibilità dal tipo di progetto  
  
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
 <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>  
 <xref:System.ArgumentException>  
 [Accesso ai servizi Web dell'applicazione](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
