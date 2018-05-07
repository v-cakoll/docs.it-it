---
title: Supporto POCO
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: ab95469afa53bd0b27efc451875d4912db74a45a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="poco-support"></a>Supporto POCO
In questo esempio viene illustrato il supporto di serializzazione per i tipi non contrassegnati, ovvero tipi ai quali non sono stati applicati attributi di serializzazione, definiti talvolta tipi di oggetto POCO (Plain Old CLR Object). Tramite <xref:System.Runtime.Serialization.DataContractSerializer> viene dedotto un contratto dati per tutti i tipi contrassegnati pubblici che dispongono di un costruttore predefinito. I contratti dati consentono di passare dati strutturati a e da i servizi. Per ulteriori informazioni sui tipi non contrassegnati, vedere [tipi serializzabili](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
 Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md), ma utilizza numeri complessi anziché i tipi numerici primitivi. È anche simile al [base contratto dati](../../../../docs/framework/wcf/samples/basic-data-contract.md) di esempio, con la differenza che il <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> non vengono utilizzati gli attributi.  
  
 Il servizio è ospitato da Internet Information Services (IIS) e il client è un'applicazione console (con estensione exe).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 La classe `ComplexNumber` viene utilizzata in `ServiceContract`. Il tipo `ComplexNumber` non dispone degli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute>, come illustrato nel codice di esempio seguente. Per impostazione predefinita, le proprietà e i campi pubblici vengono serializzati.  
  
```  
public class ComplexNumber  
{  
    public double Real;  
    public double Imaginary;  
    public ComplexNumber()  
    {  
        Real = double.MinValue;  
        Imaginary = double.MinValue;  
    }  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>  
 [Tipi serializzabili](../../../../docs/framework/wcf/feature-details/serializable-types.md)
