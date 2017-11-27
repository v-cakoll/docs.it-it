---
title: Oggetto My.WebServices
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords: My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a9f2c4017a1df8059f2cc57e7c30a96c474cfda0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="mywebservices-object"></a>Oggetto My.WebServices
Fornisce proprietà per la creazione e l'accesso a una singola istanza di ciascun servizio Web XML a cui fa riferimento il progetto corrente.  
  
## <a name="remarks"></a>Note  
 L'oggetto `My.WebServices` fornisce un'istanza di ogni servizio Web a cui si fa riferimento nel progetto corrente. Ogni istanza viene creata su richiesta. È possibile accedere a questi servizi Web tramite le proprietà dell'oggetto `My.WebServices`. Il nome della proprietà è uguale al nome del servizio Web a cui la proprietà accede. Qualsiasi classe che eredita da <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> è un servizio Web. Per informazioni sull'aggiunta dei servizi Web a un progetto, vedere [accesso ai servizi Web di applicazione](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Il `My.WebServices` oggetto espone solo i servizi Web associati al progetto corrente. Non fornisce accesso ai servizi Web dichiarati nelle DLL di cui si fa riferimento. Per accedere a un servizio Web che fornisce una DLL, è necessario utilizzare il nome completo del servizio Web, nel formato *NomeDLL*. *WebServiceName*. Per ulteriori informazioni, vedere [accesso ai servizi Web di applicazione](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 L'oggetto e le relative proprietà non sono disponibili per le applicazioni Web.  
  
## <a name="properties"></a>Proprietà  
 Ogni proprietà del `My.WebServices` oggetto consente di accedere a un'istanza di un servizio Web a cui fa riferimento il progetto corrente. Il nome della proprietà è identico al nome del servizio Web che accede a proprietà e il tipo della proprietà è identico al tipo del servizio Web.  
  
> [!NOTE]
>  Se si verifica un conflitto di nome, il nome della proprietà per l'accesso a un servizio Web è *RootNamespace*_*Namespace*\_*ServiceName*. Si consideri ad esempio due servizi Web denominati `Service1`. Se uno di questi servizi è nello spazio dei nomi radice `WindowsApplication1` e nello spazio dei nomi `Namespace1`, accedere a tale servizio utilizzando `My.WebServices.WindowsApplication1_Namespace1_Service1`.  
  
 Quando si accede a uno del `My.WebServices` proprietà dell'oggetto, crea una nuova istanza del servizio Web e viene archiviato. Gli accessi successivi di tale proprietà restituiscono tale istanza del servizio Web.  
  
 Per rimuovere un servizio Web tramite l'assegnazione `Nothing` alla proprietà per il servizio Web. Assegna il setter di proprietà `Nothing` al valore archiviato. Se si assegna un valore diverso da `Nothing` alla proprietà, il metodo set genera un <xref:System.ArgumentException> eccezione.  
  
 È possibile verificare se una proprietà del `My.WebServices` oggetto archivia un'istanza del servizio Web utilizzando il `Is` o `IsNot` operatore. È possibile utilizzare tali operatori per verificare se il valore della proprietà è `Nothing`.  
  
> [!NOTE]
>  In genere, il `Is` o `IsNot` operatore deve leggere il valore della proprietà per eseguire il confronto. Tuttavia, se il valore della proprietà è `Nothing`, la proprietà crea una nuova istanza del servizio Web e quindi restituisce tale istanza. Tuttavia, il compilatore Visual Basic gestisce le proprietà del `My.WebServices` speciale dell'oggetto e consente la `Is` o `IsNot` operatore per controllare lo stato della proprietà senza modificarne il valore.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene chiamato il `FahrenheitToCelsius` metodo il `TemperatureConverter` il servizio Web XML e restituisce il risultato.  
  
 [!code-vb[VbVbalrMyWebService#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-webservices-object_1.vb)]  
  
 Per eseguire questo esempio, il progetto deve fare riferimento a un servizio Web denominato `Converter`, e deve esporre il servizio Web di `ConvertTemperature` metodo. Per ulteriori informazioni, vedere [accesso ai servizi Web di applicazione](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Questo codice non funziona in un progetto di applicazione Web.  
  
## <a name="requirements"></a>Requisiti  
  
### <a name="availability-by-project-type"></a>Disponibilità per il tipo di progetto  
  
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
