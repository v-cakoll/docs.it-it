---
title: 'Procedura: Specificare le credenziali del Client per un servizio dati richiedono (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing requests
ms.assetid: 1632f9af-e45f-4363-9222-03823daa8e28
ms.openlocfilehash: ca2ed1fcf113e06535c8900e5836eb64f9b23958
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61875582"
---
# <a name="how-to-specify-client-credentials-for-a-data-service-request-wcf-data-services"></a>Procedura: Specificare le credenziali del Client per un servizio dati richiedono (WCF Data Services)
Per impostazione predefinita, la libreria client non fornisce le credenziali quando viene inviata una richiesta a un servizio [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Tuttavia, è possibile specificare che le credenziali vengano inviate per autenticare richieste al servizio dati fornendo un elemento <xref:System.Net.NetworkCredential> per la proprietà <xref:System.Data.Services.Client.DataServiceContext.Credentials%2A> di <xref:System.Data.Services.Client.DataServiceContext>. Per altre informazioni, vedere [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md). Nell'esempio in questo argomento viene illustrato come fornire in modo esplicito le credenziali che vengono usate dal client [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] per richiedere i dati dal servizio dati.  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). È anche possibile usare la [servizio dati Northwind di esempio](https://go.microsoft.com/fwlink/?LinkId=187426) pubblicato sul [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] sito Web; i dati di esempio servizio è di sola lettura e tenta di salvare le modifiche viene restituito un errore. Servizi dati di esempio di [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] sito Web consentire l'autenticazione anonima.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente è dalla pagina code-behind per un file di Extensible Application Markup Language (XAML) che rappresenta la pagina principale dell'applicazione Windows Presentation Framework. In questo esempio viene visualizzata un'istanza di `LoginWindow` per raccogliere le credenziali di autenticazione dall'utente e usare quindi queste credenziali per una richiesta al servizio dati.  
  
 [!code-csharp[Astoria Northwind Client#ClientCredentials](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/clientcredentials.xaml.cs#clientcredentials)]  
 [!code-vb[Astoria Northwind Client#ClientCredentials](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/clientcredentials.xaml.vb#clientcredentials)]
  
## <a name="example"></a>Esempio  
 Tramite il codice XAML seguente viene definita la pagina principale dell'applicazione WPF.  
  
 [!code-xaml[Astoria Northwind Client#ClientCredentialsXaml](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/clientcredentials.xaml#clientcredentialsxaml)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente è tratto dalla pagina code-behind per la finestra usata per raccogliere le credenziali di autenticazione dall'utente prima di effettuare una richiesta al servizio dati.  
  
 [!code-csharp[Astoria Northwind Client#ClientCredentialsLogin](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/clientcredentialslogin.xaml.cs#clientcredentialslogin)]  
 [!code-vb[Astoria Northwind Client#ClientCredentialsLogin](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/clientcredentialslogin.xaml.vb#clientcredentialslogin)]
  
## <a name="example"></a>Esempio  
 Il codice XAML seguente definisce l'accesso dell'applicazione WPF.  
  
 [!code-xaml[Astoria Northwind Client#ClientCredentialsLoginXaml](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/clientcredentialslogin.xaml#clientcredentialsloginxaml)]  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Le considerazioni sulla sicurezza riportate di seguito si applicano all'esempio di questo argomento:  
  
-   Per verificare le credenziali fornite in questo esempio, il servizio dati Northwind deve usare uno schema di autenticazione diverso dall'accesso anonimo. In caso contrario, il sito Web che ospita il servizio dati non richiederà le credenziali.  
  
-   Le credenziali utente devono essere richieste solo durante l'esecuzione e non devono essere memorizzate nella cache. Le credenziali devono essere archiviate sempre in modo protetto.  
  
-   I dati inviati con l'autenticazione di base o digest non sono crittografati, pertanto possono essere visti da un antagonista. Le credenziali di autenticazione di base (nome utente e password) inoltre vengono inviate in testo non crittografato e possono essere intercettate.  
  
 Per altre informazioni, vedere [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
## <a name="see-also"></a>Vedere anche

- [Protezione di WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)
- [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
