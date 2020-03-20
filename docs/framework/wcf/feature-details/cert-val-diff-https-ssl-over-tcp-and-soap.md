---
title: Differenze di convalida del certificato tra HTTPS, SSL su TCP e protezione SOAP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], validation differences
ms.assetid: 953a219f-4745-4019-9894-c70704f352e6
ms.openlocfilehash: 0e82d1898bec7cda474a5a92958b5af1b30c9de7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185402"
---
# <a name="certificate-validation-differences-between-https-ssl-over-tcp-and-soap-security"></a>Differenze di convalida del certificato tra HTTPS, SSL su TCP e protezione SOAP
È possibile usare i certificati in Windows Communication Foundation (WCF) con la sicurezza SOAP (Message Layer) oltre alla sicurezza a livello di trasporto (TLS) su HTTP (HTTPS) o TCP. In questo argomento vengono descritte le differenze nella modalità di convalida dei certificati.  
  
## <a name="validation-of-https-client-certificates"></a>Convalida di certificati di client HTTPS  
 In caso di utilizzo di HTTPS per la comunicazione tra un client e un servizio, il certificato utilizzato dal client per autenticare il servizio deve supportare la catena di certificati, ovvero deve concatenarsi a un'Autorità di certificazione radice attendibile. In caso contrario, il livello HTTP genera un'eccezione <xref:System.Net.WebException> con il messaggio "Errore del server remoto: (403) non consentito". WCF espone questa eccezione come <xref:System.ServiceModel.Security.MessageSecurityException>un oggetto .  
  
## <a name="validation-of-https-service-certificates"></a>Convalida di certificati di servizi HTTPS  
 In caso di utilizzo di HTTPS per la comunicazione tra un client e un servizio, il certificato autenticato dal server deve supportare la catena di certificati per impostazione predefinita, ovvero deve concatenarsi a un'Autorità di certificazione radice attendibile. Non viene eseguito alcun controllo in linea per appurare se il certificato è stato revocato. È possibile eseguire l'override di questo comportamento registrando un callback <xref:System.Net.Security.RemoteCertificateValidationCallback>, come illustrato nel codice seguente.  
  
 [!code-csharp[c_CertificateValidationDifferences#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#1)]
 [!code-vb[c_CertificateValidationDifferences#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#1)]  
  
 dove la firma per `ValidateServerCertificate` è come segue:  
  
 [!code-csharp[c_CertificateValidationDifferences#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#2)]
 [!code-vb[c_CertificateValidationDifferences#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#2)]  
  
 L'implementazione di `ValidateServerCertificate` può eseguire qualsiasi controllo che lo sviluppatore dell'applicazione client ritenga necessario per convalidare il certificato del servizio.  
  
## <a name="validation-of-client-certificates-in-ssl-over-tcp-or-soap-security"></a>Convalida di certificati client in SSL su TCP o protezione SOAP  
 Quando si utilizza SSL (Secure Sockets Layer) su TCP o la protezione dei messaggi (SOAP), i certificati client vengono convalidati secondo il valore della proprietà <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> della classe <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>. La proprietà è impostata su uno dei valori <xref:System.ServiceModel.Security.X509CertificateValidationMode>. La verifica della revoca viene eseguita secondo i valori del valore della proprietà <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.RevocationMode%2A> della classe <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>. La proprietà è impostata su uno dei valori <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.  
  
 [!code-csharp[c_CertificateValidationDifferences#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#3)]
 [!code-vb[c_CertificateValidationDifferences#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#3)]  
  
## <a name="validation-of-service-certificate-in-ssl-over-tcp-and-soap-security"></a>Convalida di certificati del servizio in SSL su TCP e protezione SOAP  
 Quando si utilizza SSL su TCP o la protezione dei messaggi (SOAP), i certificati del servizio vengono convalidati secondo il valore della proprietà <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> della classe <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>. La proprietà è impostata su uno dei valori <xref:System.ServiceModel.Security.X509CertificateValidationMode>.  
  
 La verifica della revoca viene eseguita secondo i valori del valore della proprietà <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.RevocationMode%2A> della classe <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>. La proprietà è impostata su uno dei valori <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.  
  
 [!code-csharp[c_CertificateValidationDifferences#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#4)]
 [!code-vb[c_CertificateValidationDifferences#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.Security.RemoteCertificateValidationCallback>
- [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
