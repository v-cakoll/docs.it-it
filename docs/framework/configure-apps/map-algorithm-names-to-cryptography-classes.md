---
title: Mapping di nomi di algoritmi a classi di crittografia
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: 6ec98aabd92a7a0fed11482bdf6e5e8ddc045a7e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098741"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a>Mapping di nomi di algoritmi a classi di crittografia
Sono disponibili quattro modi, uno sviluppatore può creare un oggetto di crittografia usando il [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:  
  
-   Creare un oggetto usando il **nuovo** operatore.  
  
-   Creare un oggetto che implementa un algoritmo di crittografia specifico chiamando il **Create** metodo sulla classe astratta per l'algoritmo di.  
  
-   Creare un oggetto che implementa un algoritmo di crittografia specifico chiamando il <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> (metodo).  
  
-   Crea un oggetto che implementa una classe di algoritmi di crittografia (ad esempio, una crittografia a blocchi simmetriche) chiamando il **Create** metodo sulla classe astratta per il tipo di algoritmo (ad esempio <xref:System.Security.Cryptography.SymmetricAlgorithm>).  
  
 Si supponga, ad esempio, che uno sviluppatore desidera calcolare l'hash SHA1 di un set di byte. Il <xref:System.Security.Cryptography> dello spazio dei nomi contiene due implementazioni dell'algoritmo SHA1, un'implementazione completamente gestita e quello che esegue il wrapping di CryptoAPI. Lo sviluppatore può scegliere di creare un'istanza di una particolare implementazione di SHA1 (ad esempio il <xref:System.Security.Cryptography.SHA1Managed>) chiamando il **nuovo** operatore. Tuttavia, se non è rilevante la classe a cui viene caricato common language runtime, purché la classe implementa l'algoritmo hash SHA1, lo sviluppatore può creare un oggetto chiamando il <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> (metodo). Questo metodo chiama **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, che deve restituire un'implementazione dell'algoritmo hash SHA1.  
  
 Lo sviluppatore può anche chiamare **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** perché, per impostazione predefinita, configurazione di crittografia include i nomi brevi per gli algoritmi forniti in .NET Framework.  
  
 Se non è importante l'algoritmo hash utilizzato, lo sviluppatore può chiamare il <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> metodo, che restituisce un oggetto che implementa una trasformazione basata su hash.  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a>Mapping di nomi di algoritmo nei file di configurazione  
 Per impostazione predefinita, viene restituito un <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> oggetto per tutti i quattro scenari. Tuttavia, un amministratore del computer è possibile modificare il tipo dell'oggetto restituite dai metodi negli ultimi due scenari. A tale scopo, è necessario mappare un nome di algoritmo descrittivo per la classe da usare nel file di configurazione del computer (Machine. config).  
  
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
  
 È possibile specificare il nome dell'attributo nel [< cryptoClass\> elemento](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (nell'esempio precedente i nomi di attributo `MySHA1Hash`). Il valore dell'attributo nel  **\<cryptoClass >** elemento è una stringa che common language runtime usa per trovare la classe. È possibile usare qualsiasi stringa che soddisfi i requisiti specificati nelle [Specifying Fully Qualified Type Names](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).  
  
 Molti dei nomi degli algoritmi può eseguire il mapping alla stessa classe. Il [ \<nameEntry > elemento](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) esegue il mapping di una classe a un nome descrittivo di algoritmo. Il **name** attributo può essere una stringa che viene usata quando si chiama il **CreateFromName** metodo o il nome di una classe astratta di crittografia nel <xref:System.Security.Cryptography> dello spazio dei nomi. Il valore della **classe** attributo è il nome dell'attributo nel  **\<cryptoClass >** elemento.  
  
> [!NOTE]
>  È possibile ottenere un algoritmo SHA1 chiamando il <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> o il **Security.CryptoConfig.CreateFromName("SHA1")** (metodo). Ogni metodo assicura solo che restituisce un oggetto che implementa l'algoritmo SHA1. Non è necessario eseguire il mapping di ogni nome descrittivo di un algoritmo per la stessa classe nel file di configurazione.  
  
 Per un elenco di nomi predefiniti e le classi di cui eseguono il mapping, vedere <xref:System.Security.Cryptography.CryptoConfig>.  
  
## <a name="see-also"></a>Vedere anche

- [servizi crittografici](../../../docs/standard/security/cryptographic-services.md)
- [Configurazione di classi di crittografia](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
