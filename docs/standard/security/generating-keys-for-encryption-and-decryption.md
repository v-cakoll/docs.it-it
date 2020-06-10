---
title: Generazione di chiavi per crittografia e decrittografia
description: Informazioni su come creare e gestire chiavi simmetriche e asimmetriche per la crittografia e la decrittografia in .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys, encryption and decryption
- keys, asymmetric
- keys, symmetric
- encryption [.NET Framework], keys
- symmetric keys
- asymmetric keys [.NET Framework]
- cryptography [.NET Framework], keys
ms.assetid: c197dfc9-a453-4226-898d-37a16638056e
ms.openlocfilehash: f8c3633d18e200037235502487d0d91d42083241
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84661809"
---
# <a name="generating-keys-for-encryption-and-decryption"></a>Generazione di chiavi per crittografia e decrittografia
La creazione e la gestione di chiavi sono due momenti importanti del processo di crittografia. Per gli algoritmi simmetrici è richiesta la creazione di una chiave e un vettore di inizializzazione (IV). La chiave deve rimanere segreta per chiunque non debba decrittografare i dati. Il vettore di inizializzazione non deve rimanere segreto, ma dovrebbe essere modificato per ogni sessione. Gli algoritmi asimmetrici richiedono la creazione di una chiave pubblica e di una chiave privata. La chiave pubblica può essere resa pubblica a chiunque, mentre quella privata deve essere nota solo alla parte che decrittograferà i dati crittografati con la chiave pubblica. Questa sezione descrive come generare e gestire chiavi sia per gli algoritmi simmetrici che per quelli asimmetrici.  
  
## <a name="symmetric-keys"></a>Chiavi simmetriche  
 Le classi di crittografia simmetrica disponibili in .NET Framework richiedono una chiave e un nuovo vettore di inizializzazione (IV, Initialization Vector) per crittografare e decrittografare i dati. Ogni volta che si crea una nuova istanza di una delle classi crittografiche simmetriche gestite usando il costruttore senza parametri, vengono create automaticamente una nuova chiave e un vettore di inizializzazione. Per riuscire a decrittografare i dati, i destinatari devono avere la stessa chiave e lo stesso vettore di inizializzazione e devono usare il medesimo algoritmo di crittografia. Generalmente è necessario creare una chiave e un vettore di inizializzazione nuovi per ogni sessione e né la chiave né il vettore devono essere archiviati per un uso in una sessione successiva.  
  
 Per comunicare una chiave simmetrica e un vettore di inizializzazione a una parte remota, la chiave simmetrica viene generalmente crittografata mediante la crittografia asimmetrica. L'invio della chiave in una rete non protetta senza crittografarla non è sicuro, poiché chiunque intercetti la chiave e il vettore di inizializzazione è in grado di decrittografare i dati. Per ulteriori informazioni sullo scambio di dati utilizzando la crittografia, vedere [Creare uno schema di crittografia](creating-a-cryptographic-scheme.md).  
  
 L'esempio seguente illustra la creazione di una nuova istanza della classe <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> che implementa l'algoritmo TripleDES.  
  
```vb  
Dim tdes As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
```  
  
```csharp  
TripleDESCryptoServiceProvider tdes = new TripleDESCryptoServiceProvider();  
```  
  
 Quando viene eseguito il codice precedente, una chiave e un vettore di inizializzazione nuovi vengono generati e inseriti rispettivamente nelle proprietà **Key** e **IV** .  
  
 Talvolta può essere necessario generare più chiavi. In questa situazione è possibile creare una nuova istanza di una classe che implementa un algoritmo simmetrico e quindi creare una chiave e un vettore di inizializzazione nuovi chiamando i metodi **GenerateKey** e **GenerateIV** . Nell'esempio di codice seguente viene illustrato come creare nuove chiavi e IV dopo che è stata creata una nuova istanza della classe di crittografia simmetrica.  
  
```vb  
Dim tdes As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
tdes.GenerateIV()  
tdes.GenerateKey()  
```  
  
```csharp  
TripleDESCryptoServiceProvider tdes = new TripleDESCryptoServiceProvider();  
tdes.GenerateIV();  
tdes.GenerateKey();  
```  
  
 Quando viene eseguito il codice precedente, una chiave e un vettore di inizializzazione nuovi vengono generati quando viene creata la nuova istanza di **TripleDESCryptoServiceProvider** . Un'altra chiave e vettore di inizializzazione vengono creati quando vengono chiamati i metodi **GenerateKey** e **GenerateIV** .  
  
## <a name="asymmetric-keys"></a>Chiavi asimmetriche  
 In .NET Framework sono incluse le classi <xref:System.Security.Cryptography.RSACryptoServiceProvider> e <xref:System.Security.Cryptography.DSACryptoServiceProvider> per la crittografia asimmetrica. Queste classi creano una coppia di chiavi pubblica/privata quando si usa il costruttore senza parametri per creare una nuova istanza. Le chiavi asimmetriche possono essere archiviate per un uso in più sessioni o generate per una sola sessione. Mentre la chiave pubblica può essere generalmente resa disponibile, la chiave privata va custodita con cura.  
  
 Una coppia di chiavi pubblica/privata viene generata ogni volta che viene creata una nuova istanza di una classe di algoritmo asimmetrico. Dopo che è stata creata una nuova istanza della classe, le informazioni sulla chiave possono essere estratte con uno dei metodi indicati di seguito:  
  
- Il metodo <xref:System.Security.Cryptography.RSA.ToXmlString%2A> , che restituisce una rappresentazione XML delle informazioni sulla chiave.  
  
- Il metodo <xref:System.Security.Cryptography.RSACryptoServiceProvider.ExportParameters%2A> , che restituisce una struttura <xref:System.Security.Cryptography.RSAParameters> contenente le informazioni sulla chiave.  
  
 Entrambi i metodi accettano un valore Boolean che indica se restituire solo le informazioni sulla chiave pubblica o le informazioni sia sulla chiave pubblica che sulla chiave privata. Una classe **RSACryptoServiceProvider** può essere inizializzata in base al valore di una struttura **RSAParameters** usando il metodo <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A> .  
  
 Le chiavi private asimmetriche non devono essere mai archiviate in modalità verbatim o in testo normale nel computer locale. Se è necessario archiviare una chiave privata, è opportuno usare un contenitore di chiavi. Per altre informazioni su come archiviare una chiave privata in un contenitore di chiavi, vedere [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).  
  
 L'esempio di codice seguente crea una nuova istanza della classe **RSACryptoServiceProvider** , che crea una coppia di chiavi pubblica/privata e salva le informazioni sulla chiave pubblica in una struttura **RSAParameters** .  
  
```vb  
'Generate a public/private key pair.  
Dim rsa as RSACryptoServiceProvider = new RSACryptoServiceProvider()  
'Save the public key information to an RSAParameters structure.  
Dim rsaKeyInfo As RSAParameters = rsa.ExportParameters(false)  
```  
  
```csharp  
//Generate a public/private key pair.  
RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();  
//Save the public key information to an RSAParameters structure.  
RSAParameters rsaKeyInfo = rsa.ExportParameters(false);  
```  
  
## <a name="see-also"></a>Vedere anche

- [Encrypting Data](encrypting-data.md)
- [Decrittografia di dati](decrypting-data.md)
- [Servizi di crittografia](cryptographic-services.md)
- [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md)
