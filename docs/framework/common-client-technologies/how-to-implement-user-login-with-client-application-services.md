---
title: "Procedura: implementare l'accesso utente con i servizi dell'applicazione client"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating users [client application services]
- validation [.NET Framework], client application services
- client application services, authenticate users
ms.assetid: 5431a671-eb02-4e18-a651-24764fccec9a
ms.openlocfilehash: 1b1c5bebb5bd94f0a56dc6da303ef2503ab6dd4f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743810"
---
# <a name="how-to-implement-user-login-with-client-application-services"></a>Procedura: implementare l'accesso utente con i servizi dell'applicazione client
È possibile usare i servizi delle applicazioni client per convalidare gli utenti tramite un servizio profili [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] esistente. Per informazioni su come configurare il servizio di profili [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)], vedere l'argomento relativo all[Uso dell'autenticazione basata su modulo con Microsoft Ajax](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e).  
  
 Le procedure seguenti descrivono come convalidare gli utenti tramite il servizio di autenticazione quando l'applicazione è configurata per usare uno dei provider di servizi di autenticazione client. Per altre informazioni, vedere [Procedura: Configurare i servizi delle applicazioni client](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).  
  
 Tutte le convalide vengono in genere eseguite tramite il metodo `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType>. Questo metodo gestisce l'interazione con il servizio di autenticazione tramite il provider di autenticazione configurato. Per altre informazioni, vedere [Cenni preliminari sui servizi delle applicazioni client](../../../docs/framework/common-client-technologies/client-application-services-overview.md).  
  
 Le procedure di autenticazione basate su modulo richiedono l'accesso a un servizio di autenticazione [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] in esecuzione. Per istruzioni sul test end-to-end delle funzionalità dei servizi dell'applicazione client, vedere [Procedura dettagliata: Uso di servizi delle applicazioni client](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md).  
  
### <a name="to-authenticate-a-user-with-forms-authentication-using-a-membership-credentials-provider"></a>Per autenticare un utente con autenticazione basata su form usando un provider di credenziali di appartenenza  
  
1.  Implementare l'interfaccia <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>. L’esempio di codice seguente mostra un’implementazione <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A?displayProperty=nameWithType> per una classe di una finestra di dialogo di accesso derivata da <xref:System.Windows.Forms.Form?displayProperty=nameWithType>. In questa finestra di dialogo vi sono caselle di testo per il nome utente e la password e una casella di controllo di memorizzazione dei dati. Quando il provider di autenticazione client chiama il metodo <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A>, il form viene visualizzato. Quando l'utente inserisce le informazioni nella finestra di dialogo di accesso e fa clic su OK, vengono restituiti i valori specificati in un nuovo oggetto <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>.  
  
     [!code-csharp[ClientApplicationServices#210](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Login.cs#210)]
     [!code-vb[ClientApplicationServices#210](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#210)]  
  
2.  Chiamare il metodo `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> e passare stringhe vuote come valori del parametro. Quando si specificano stringhe vuote, questo metodo chiama internamente il metodo <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> per il provider di credenziali configurato per l'applicazione. Il codice di esempio seguente chiama questo metodo per limitare l’accesso a un’intera applicazione Windows Form. È possibile aggiungere questo codice per un gestore <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>.  
  
     [!code-csharp[ClientApplicationServices#317](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#317)]
     [!code-vb[ClientApplicationServices#317](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#317)]  
  
### <a name="to-authenticate-a-user-with-forms-authentication-without-using-a-membership-credentials-provider"></a>Per autenticare un utente con autenticazione basata su form senza usare un provider di credenziali di appartenenza  
  
-   Chiamare il metodo `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> e passare i valori di nome utente e password recuperati dall'utente.  
  
     [!code-csharp[ClientApplicationServices#318](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#318)]
     [!code-vb[ClientApplicationServices#318](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#318)]  
  
### <a name="to-authenticate-a-user-with-windows-authentication"></a>Per autenticare un utente con l’autenticazione di Windows  
  
-   Chiamare il metodo `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> e passare stringhe vuote per i parametri. Questa chiamata al metodo restituirà sempre `true` e aggiungerà un cookie alla cache dei cookie dell'utente che contiene l'identità di Windows.  
  
     [!code-csharp[ClientApplicationServices#319](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#319)]
     [!code-vb[ClientApplicationServices#319](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#319)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Il codice di esempio in questo argomento illustra gli usi di autenticazione più semplici in un’applicazione client Windows. Quando si chiama il metodo `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> con i servizi delle applicazioni client e l’autenticazione basata su form, il codice può tuttavia generare un'eccezione <xref:System.Net.WebException>. Ciò indica che il servizio di autenticazione non è disponibile. Per un esempio su come gestire questa eccezione, vedere [Procedura dettagliata: Uso dei servizi delle applicazioni client](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Servizi applicazioni client](../../../docs/framework/common-client-technologies/client-application-services.md)  
 [Cenni preliminari sui servizi delle applicazioni client](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 [Procedura: Configurare i servizi delle applicazioni client](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 [Procedura dettagliata: uso di servizi delle applicazioni client](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 [Uso dell'autenticazione basata su form con Microsoft Ajax](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)
