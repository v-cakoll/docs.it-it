---
title: Mapping di nomi di algoritmi a classi di crittografia
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e59b2551545b8b70bcb54a5d43d041c44579b786
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a>Mapping di nomi di algoritmi a classi di crittografia
Esistono quattro modi diversi, uno sviluppatore può creare un oggetto di crittografia utilizzando il [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:  
  
-   Creare un oggetto utilizzando il **nuova** operatore.  
  
-   Creare un oggetto che implementa un determinato algoritmo di crittografia tramite la chiamata di **crea** metodo sulla classe astratta per l'algoritmo di.  
  
-   Creare un oggetto che implementa un determinato algoritmo di crittografia tramite la chiamata di <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo.  
  
-   Creare un oggetto che implementa una classe di algoritmi di crittografia (ad esempio una crittografia a blocchi simmetrica) chiamando il **crea** metodo sulla classe astratta per il tipo di algoritmo (ad esempio <xref:System.Security.Cryptography.SymmetricAlgorithm>).  
  
 Si supponga, ad esempio, che uno sviluppatore desidera calcolare l'hash SHA1 di un set di byte. Il <xref:System.Security.Cryptography> dello spazio dei nomi contiene due implementazioni dell'algoritmo SHA1, un'implementazione semplicemente gestita e uno che esegue il wrapping di CryptoAPI. Lo sviluppatore può scegliere di creare un'istanza di una determinata implementazione SHA1 (ad esempio il <xref:System.Security.Cryptography.SHA1Managed>) chiamando il **nuova** operatore. Tuttavia, se non è rilevante la classe a cui viene caricato common language runtime, purché la classe implementa l'algoritmo hash SHA1, lo sviluppatore può creare un oggetto chiamando il <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> metodo. Questo metodo chiama **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, che deve restituire un'implementazione dell'algoritmo hash SHA1.  
  
 Lo sviluppatore può anche chiamare **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** perché, per impostazione predefinita, sistema di configurazione include i nomi brevi per gli algoritmi forniti in .NET Framework.  
  
 Se non è importante algoritmo hash utilizzato, lo sviluppatore può chiamare il <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> metodo, che restituisce un oggetto che implementa una trasformazione di hash.  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a>Mapping di nomi di algoritmo nei file di configurazione  
 Per impostazione predefinita, viene restituito un <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> in tutti e quattro gli scenari. Tuttavia, un amministratore del computer è possibile modificare il tipo di oggetto restituite dai metodi negli ultimi due scenari. A tale scopo, è necessario mappare un nome descrittivo di algoritmo per la classe a cui che si desidera utilizzare nel file di configurazione del computer (Machine. config).  
  
 Nell'esempio seguente viene illustrato come configurare il runtime in modo che **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, e  **HashAlgorithm** restituiscono un `MySHA1HashClass` oggetto.  
  
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
  
 È possibile specificare il nome dell'attributo di [< cryptoClass\> elemento](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (nell'esempio precedente i nomi di attributo `MySHA1Hash`). Il valore dell'attributo di  **\<cryptoClass >** elemento è una stringa che common language runtime utilizza per individuare la classe. È possibile utilizzare qualsiasi stringa che soddisfi i requisiti indicati [specifica di nomi di tipo completi](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).  
  
 Molti nomi di algoritmo possono eseguire il mapping alla stessa classe. Il [ \<nameEntry > elemento](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) esegue il mapping di una classe a un nome descrittivo di algoritmo. Il **nome** attributo può essere una stringa che viene utilizzata quando si chiama il **CreateFromName** metodo o il nome di una classe astratta di crittografia nel <xref:System.Security.Cryptography> dello spazio dei nomi. Il valore di **classe** attributo è il nome dell'attributo nel  **\<cryptoClass >** elemento.  
  
> [!NOTE]
>  È possibile ottenere un algoritmo SHA1 chiamando il <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> o **Security.CryptoConfig.CreateFromName("SHA1")** metodo. Ogni metodo assicura solo che restituisce un oggetto che implementa l'algoritmo SHA1. Non è necessario eseguire il mapping di ogni nome di un algoritmo alla stessa classe nel file di configurazione.  
  
 Per un elenco dei nomi predefiniti e le classi a cui viene eseguito il mapping, vedere <xref:System.Security.Cryptography.CryptoConfig>.  
  
## <a name="see-also"></a>Vedere anche  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
 [Configurazione di classi di crittografia](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
