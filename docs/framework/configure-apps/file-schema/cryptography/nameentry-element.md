---
title: <nameEntry> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: b5f92ca2956f32382b12c9a1dec4e5d41ea4ee2a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285927"
---
# <a name="nameentry-element"></a>\<nameEntry > elemento
Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.  
  
 \<configuration>  
\<mscorlib>  
\<cryptographySettings>  
\<cryptoNameMapping>  
\<nameEntry>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|**name**|Attributo obbligatorio.<br /><br /> Specifica il nome descrittivo dell'algoritmo che implementa la classe di crittografia.|  
|**class**|Attributo obbligatorio.<br /><br /> Specifica il valore per il **name** attributo il [ \<cryptoClass >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) elemento.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.web`|Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.|  
  
## <a name="remarks"></a>Note  
 Il **name** attributo può essere il nome di una delle classi astratte trovate nel <xref:System.Security.Cryptography> dello spazio dei nomi. Quando si chiama il **Create** metodo su una classe astratta di crittografia, il nome di classe astratta viene passato per il <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> (metodo). **CreateFromName** restituisce un'istanza del tipo indicato per il **classe** attributo. Se il **name** attributo è un nome breve, ad esempio RSA, è possibile usare questo nome quando si chiama il **CreateFromName** (metodo).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il  **\<nameEntry >** elemento a cui fare riferimento a una classe di crittografia e configurare il runtime. È quindi possibile passare la stringa "RSA" per il <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo e usare il <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> metodo restituisca un `MyCryptoRSAClass` oggetto.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Schema delle impostazioni di crittografia](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [Cryptographic Services](../../../../../docs/standard/security/cryptographic-services.md)
- [Configurazione di classi di crittografia](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
