---
title: Mapping di nomi di algoritmi a classi di crittografia
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: 513000169504473aa6dd46feaca214f58502ffd0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912873"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a>Mapping di nomi di algoritmi a classi di crittografia
Esistono quattro modi per creare un oggetto di crittografia usando il Windows SDK:  
  
- Creare un oggetto usando l'operatore **New** .  
  
- Creare un oggetto che implementa un algoritmo di crittografia particolare chiamando il metodo **create** sulla classe astratta per tale algoritmo.  
  
- Creare un oggetto che implementa un algoritmo di crittografia particolare chiamando il <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo.  
  
- Creare un oggetto che implementi una classe di algoritmi di crittografia, ad esempio una crittografia a blocchi simmetrica, chiamando il metodo **create** sulla classe astratta per quel tipo di algoritmo (ad esempio <xref:System.Security.Cryptography.SymmetricAlgorithm>).  
  
 Si supponga, ad esempio, che uno sviluppatore desideri calcolare l'hash SHA1 di un set di byte. Lo <xref:System.Security.Cryptography> spazio dei nomi contiene due implementazioni dell'algoritmo SHA1, un'implementazione gestita esclusivamente e una che esegue il wrapping di CryptoAPI. Lo sviluppatore può scegliere di creare un'istanza di un'implementazione SHA1 specifica, ad <xref:System.Security.Cryptography.SHA1Managed>esempio, chiamando l'operatore **New** . Tuttavia, se non è importante la classe caricata da Common Language Runtime a condizione che la classe implementi l'algoritmo hash SHA1, lo sviluppatore può creare un oggetto chiamando il <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> metodo. Questo metodo chiama **System. Security. Cryptography. CryptoConfig. CreateFromName ("System. Security. Cryptography. SHA1")** , che deve restituire un'implementazione dell'algoritmo hash SHA1.  
  
 Lo sviluppatore può anche chiamare **System. Security. Cryptography. CryptoConfig. CreateFromName ("SHA1")** perché, per impostazione predefinita, la configurazione della crittografia include nomi brevi per gli algoritmi forniti nell'.NET Framework.  
  
 Se non è rilevante l'algoritmo hash usato, lo sviluppatore può chiamare il <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> metodo, che restituisce un oggetto che implementa una trasformazione hash.  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a>Mapping dei nomi degli algoritmi nei file di configurazione  
 Per impostazione predefinita, il runtime restituisce <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> un oggetto per tutti e quattro gli scenari. Un amministratore del computer può tuttavia modificare il tipo di oggetto restituito dai metodi negli ultimi due scenari. A tale scopo, è necessario eseguire il mapping di un nome di algoritmo descrittivo alla classe che si desidera utilizzare nel file di configurazione del computer (Machine. config).  
  
 Nell'esempio seguente viene illustrato come configurare il runtime in modo che **System. Security. Cryptography. SHA1. Create**, **System. Security. CryptoConfig. CREATEFROMNAME ("SHA1")** e **System. Security. Cryptography. HashAlgorithm. Create** restituisce un `MySHA1HashClass` oggetto.  
  
```xml  
<configuration>  
   <!-- Other configuration settings. -->  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MySHA1Hash="MySHA1HashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="SHA1" class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.SHA1"  
                       class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MySHA1Hash"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 È possibile specificare il nome dell'attributo nell' [elemento < CryptoClass\> ](./file-schema/cryptography/cryptoclass-element.md) (l'esempio precedente assegna un nome all'attributo `MySHA1Hash`). Il valore dell'attributo nell'  **\<elemento > CryptoClass** è una stringa utilizzata dal Common Language Runtime per trovare la classe. È possibile usare qualsiasi stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../reflection-and-codedom/specifying-fully-qualified-type-names.md).  
  
 Molti nomi di algoritmi possono essere mappati alla stessa classe. L' [ \<elemento > nameEntry](./file-schema/cryptography/nameentry-element.md) esegue il mapping di una classe a un nome di algoritmo descrittivo. L'attributo **Name** può essere una stringa utilizzata quando si chiama il metodo **System. Security. Cryptography. CryptoConfig. CreateFromName** o il nome di una <xref:System.Security.Cryptography> classe di crittografia astratta nello spazio dei nomi. Il valore dell'attributo **Class** è il nome dell'attributo nell'  **\<elemento > CryptoClass** .  
  
> [!NOTE]
> È possibile ottenere un algoritmo SHA1 chiamando il <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> metodo o il metodo **Security. CryptoConfig. CreateFromName ("SHA1")** . Ogni metodo garantisce solo che restituisca un oggetto che implementa l'algoritmo SHA1. Non è necessario eseguire il mapping di ogni nome descrittivo di un algoritmo alla stessa classe nel file di configurazione.  
  
 Per un elenco di nomi predefiniti e le classi a cui eseguono il mapping <xref:System.Security.Cryptography.CryptoConfig>, vedere.  
  
## <a name="see-also"></a>Vedere anche

- [Cryptographic Services](../../standard/security/cryptographic-services.md)
- [Configurazione di classi di crittografia](configure-cryptography-classes.md)
