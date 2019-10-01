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
ms.openlocfilehash: a339638587f8b544bbc1b0073553f6232ce09694
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699784"
---
# <a name="nameentry-element"></a>Elemento > \<nameEntry
Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<cryptographySettings >** ](cryptographysettings-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<cryptoNameMapping >** ](cryptonamemapping-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<nameEntry >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|**name**|Attributo obbligatorio.<br /><br /> Specifica il nome descrittivo dell'algoritmo implementato dalla classe di crittografia.|  
|**class**|Attributo obbligatorio.<br /><br /> Specifica il valore per l'attributo **Name** nell'elemento [> \<cryptoClass](cryptoclass-element.md) .|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.web`|Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.|  
  
## <a name="remarks"></a>Note  
 L'attributo **Name** può essere il nome di una delle classi astratte trovate nello spazio dei nomi <xref:System.Security.Cryptography>. Quando si chiama il metodo **create** in una classe di crittografia astratta, il nome della classe astratta viene passato al metodo <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>. **CreateFromName** restituisce un'istanza del tipo indicato dall'attributo **Class** . Se l'attributo **Name** è un nome breve, ad esempio RSA, è possibile usare tale nome quando si chiama il metodo **CreateFromName** .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l'elemento **> \<nameEntry** per fare riferimento a una classe di crittografia e configurare il Runtime. È quindi possibile passare la stringa "RSA" al metodo <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> e usare il metodo <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> per restituire un oggetto `MyCryptoRSAClass`.  
  
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

- [Schema dei file di configurazione](../index.md)
- [Schema delle impostazioni di crittografia](index.md)
- [Cryptographic Services](../../../../standard/security/cryptographic-services.md)
- [Configurazione di classi di crittografia](../../configure-cryptography-classes.md)
