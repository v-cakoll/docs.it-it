---
title: 'Procedura: Ospitare un servizio WCF scritto con .NET Framework 3.5 in IIS in esecuzione in .NET Framework 4'
ms.date: 03/30/2017
ms.assetid: 9aabc785-068d-4d32-8841-3ef39308d8d6
ms.openlocfilehash: 6a87fd5e3997e9d15810a5efb079da629908f854
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291531"
---
# <a name="how-to-host-a-wcf-service-written-with-net-framework-35-in-iis-running-under-net-framework-4"></a>Procedura: Ospitare un servizio WCF scritto con .NET Framework 3.5 in IIS in esecuzione in .NET Framework 4
Quando si ospita un servizio Windows Communication Foundation (WCF) scritto con [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)] in un computer che esegue [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], è possibile ottenere un <xref:System.ServiceModel.ProtocolException> con il testo seguente.  
  
```output  
Unhandled Exception: System.ServiceModel.ProtocolException: The content type text/html; charset=utf-8 of the response message does not match the content type of the binding (application/soap+xml; charset=utf-8). If using a custom encoder, be sure that the IsContentTypeSupported method is implemented properly. The first 1024 bytes of the response were: '<html>    <head>        <title>The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.</title>...  
```  
  
 Se in alternativa si tenta di passare al file con estensione svc del servizio, è possibile visualizzare una pagina di errore con il testo indicato di seguito.  
  
```output  
The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.  
```  
  
 Questi errori si verificano poiché il dominio di applicazione all'interno del quale è in esecuzione IIS esegue [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] e il servizio WCF è in attesa di esecuzione in [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]. In questo argomento vengono illustrate le modifiche necessarie per eseguire il servizio.  
  
 Trovare quindi l'elemento > < `compilers` e modificare l'opzione del provider CompilerVersion in modo che abbia un valore di 4,0. Per impostazione predefinita, sono presenti due elementi di > `compiler` < nell'elemento < `compilers` >. È necessario aggiornare l'opzione di provider CompilerVersion per entrambi gli elementi, come indicato nell'esempio seguente.  
  
```xml  
<system.codedom>  
      <compilers>  
        <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                  type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
        <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                  type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="OptionInfer" value="true"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
      </compilers>  
    </system.codedom>  
```  
  
### <a name="add-the-required-targetframework-attribute"></a>Aggiungere l'attributo targetFramework obbligatorio  
  
1. Aprire il file Web. config del servizio e cercare l'elemento > < `compilation`.  
  
2. Aggiungere l'attributo `targetFramework` all'elemento < > `compilation`, come illustrato nell'esempio seguente.  
  
    ```xml  
    <compilation debug="false"  
            targetFramework="4.0">  
  
            <assemblies>  
              <add assembly="System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Xml.Linq, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Web.Extensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35"/>  
              <add assembly="System.Data.DataSetExtensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
            </assemblies>  
  
          </compilation>  
    ```  
  
3. Trovare l'elemento > < `compilers` e modificare l'opzione del provider CompilerVersion in modo che abbia un valore di 4,0. Per impostazione predefinita, sono presenti due elementi di > `compiler` < nell'elemento < `compilers` >. È necessario aggiornare l'opzione di provider CompilerVersion per entrambi gli elementi, come indicato nell'esempio seguente.  
  
    ```xml  
    <system.codedom>  
          <compilers>  
            <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                      type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
            <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                      type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="OptionInfer" value="true"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
          </compilers>  
        </system.codedom>  
    ```
