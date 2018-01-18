---
title: Raccolte di schemi OLE DB
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 33e794559abd7f619f7431683f06e59705b57d41
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="5c4ad-102">Raccolte di schemi OLE DB</span><span class="sxs-lookup"><span data-stu-id="5c4ad-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="5c4ad-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per i provider OLE DB per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="5c4ad-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="5c4ad-104">Provider OLE DB per Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c4ad-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="5c4ad-105">Il Driver OLE DB Microsoft SQL Server supporta le raccolte di schemi specifici seguenti oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="5c4ad-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="5c4ad-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="5c4ad-106">Tables</span></span>  
  
-   <span data-ttu-id="5c4ad-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="5c4ad-107">Columns</span></span>  
  
-   <span data-ttu-id="5c4ad-108">Procedure</span><span class="sxs-lookup"><span data-stu-id="5c4ad-108">Procedures</span></span>  
  
-   <span data-ttu-id="5c4ad-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="5c4ad-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="5c4ad-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="5c4ad-110">Catalog</span></span>  
  
-   <span data-ttu-id="5c4ad-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="5c4ad-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="5c4ad-112">Tabelle</span><span class="sxs-lookup"><span data-stu-id="5c4ad-112">Tables</span></span>  
  
|<span data-ttu-id="5c4ad-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-113">ColumnName</span></span>|<span data-ttu-id="5c4ad-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-115">TABLE_CATALOG</span></span>|<span data-ttu-id="5c4ad-116">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-116">String</span></span>|  
|<span data-ttu-id="5c4ad-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="5c4ad-118">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-118">String</span></span>|  
|<span data-ttu-id="5c4ad-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-119">TABLE_NAME</span></span>|<span data-ttu-id="5c4ad-120">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-120">String</span></span>|  
|<span data-ttu-id="5c4ad-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-121">TABLE_TYPE</span></span>|<span data-ttu-id="5c4ad-122">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-122">String</span></span>|  
|<span data-ttu-id="5c4ad-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-123">TABLE_GUID</span></span>|<span data-ttu-id="5c4ad-124">Guid</span><span class="sxs-lookup"><span data-stu-id="5c4ad-124">Guid</span></span>|  
|<span data-ttu-id="5c4ad-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-125">DESCRIPTION</span></span>|<span data-ttu-id="5c4ad-126">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-126">String</span></span>|  
|<span data-ttu-id="5c4ad-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-127">TABLE_PROPID</span></span>|<span data-ttu-id="5c4ad-128">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-128">Int64</span></span>|  
|<span data-ttu-id="5c4ad-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-129">DATE_CREATED</span></span>|<span data-ttu-id="5c4ad-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c4ad-130">DateTime</span></span>|  
|<span data-ttu-id="5c4ad-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-131">DATE_MODIFIED</span></span>|<span data-ttu-id="5c4ad-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c4ad-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="5c4ad-133">Colonne</span><span class="sxs-lookup"><span data-stu-id="5c4ad-133">Columns</span></span>  
  
|<span data-ttu-id="5c4ad-134">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-134">ColumnName</span></span>|<span data-ttu-id="5c4ad-135">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-136">TABLE_CATALOG</span></span>|<span data-ttu-id="5c4ad-137">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-137">String</span></span>|  
|<span data-ttu-id="5c4ad-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="5c4ad-139">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-139">String</span></span>|  
|<span data-ttu-id="5c4ad-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-140">TABLE_NAME</span></span>|<span data-ttu-id="5c4ad-141">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-141">String</span></span>|  
|<span data-ttu-id="5c4ad-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-142">COLUMN_NAME</span></span>|<span data-ttu-id="5c4ad-143">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-143">String</span></span>|  
|<span data-ttu-id="5c4ad-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-144">COLUMN_GUID</span></span>|<span data-ttu-id="5c4ad-145">Guid</span><span class="sxs-lookup"><span data-stu-id="5c4ad-145">Guid</span></span>|  
|<span data-ttu-id="5c4ad-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-146">COLUMN_PROPID</span></span>|<span data-ttu-id="5c4ad-147">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-147">Int64</span></span>|  
|<span data-ttu-id="5c4ad-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="5c4ad-149">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-149">Int64</span></span>|  
|<span data-ttu-id="5c4ad-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="5c4ad-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="5c4ad-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-151">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="5c4ad-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="5c4ad-153">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-153">String</span></span>|  
|<span data-ttu-id="5c4ad-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="5c4ad-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="5c4ad-155">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-155">Int64</span></span>|  
|<span data-ttu-id="5c4ad-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-156">IS_NULLABLE</span></span>|<span data-ttu-id="5c4ad-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-157">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-158">DATA_TYPE</span></span>|<span data-ttu-id="5c4ad-159">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-159">Int32</span></span>|  
|<span data-ttu-id="5c4ad-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-160">TYPE_GUID</span></span>|<span data-ttu-id="5c4ad-161">Guid</span><span class="sxs-lookup"><span data-stu-id="5c4ad-161">Guid</span></span>|  
|<span data-ttu-id="5c4ad-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5c4ad-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="5c4ad-163">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-163">Int64</span></span>|  
|<span data-ttu-id="5c4ad-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5c4ad-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="5c4ad-165">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-165">Int64</span></span>|  
|<span data-ttu-id="5c4ad-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="5c4ad-167">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-167">Int32</span></span>|  
|<span data-ttu-id="5c4ad-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="5c4ad-169">Int16</span><span class="sxs-lookup"><span data-stu-id="5c4ad-169">Int16</span></span>|  
|<span data-ttu-id="5c4ad-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="5c4ad-171">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-171">Int64</span></span>|  
|<span data-ttu-id="5c4ad-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="5c4ad-173">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-173">String</span></span>|  
|<span data-ttu-id="5c4ad-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="5c4ad-175">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-175">String</span></span>|  
|<span data-ttu-id="5c4ad-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="5c4ad-177">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-177">String</span></span>|  
|<span data-ttu-id="5c4ad-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="5c4ad-179">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-179">String</span></span>|  
|<span data-ttu-id="5c4ad-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="5c4ad-181">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-181">String</span></span>|  
|<span data-ttu-id="5c4ad-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-182">COLLATION_NAME</span></span>|<span data-ttu-id="5c4ad-183">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-183">String</span></span>|  
|<span data-ttu-id="5c4ad-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="5c4ad-185">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-185">String</span></span>|  
|<span data-ttu-id="5c4ad-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="5c4ad-187">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-187">String</span></span>|  
|<span data-ttu-id="5c4ad-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-188">DOMAIN_NAME</span></span>|<span data-ttu-id="5c4ad-189">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-189">String</span></span>|  
|<span data-ttu-id="5c4ad-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-190">DESCRIPTION</span></span>|<span data-ttu-id="5c4ad-191">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-191">String</span></span>|  
|<span data-ttu-id="5c4ad-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-192">COLUMN_LCID</span></span>|<span data-ttu-id="5c4ad-193">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-193">Int32</span></span>|  
|<span data-ttu-id="5c4ad-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="5c4ad-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="5c4ad-195">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-195">Int32</span></span>|  
|<span data-ttu-id="5c4ad-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-196">COLUMN_SORTID</span></span>|<span data-ttu-id="5c4ad-197">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-197">Int32</span></span>|  
|<span data-ttu-id="5c4ad-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="5c4ad-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="5c4ad-199">Byte[]</span></span>|  
|<span data-ttu-id="5c4ad-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-200">IS_COMPUTED</span></span>|<span data-ttu-id="5c4ad-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="5c4ad-202">Procedure</span><span class="sxs-lookup"><span data-stu-id="5c4ad-202">Procedures</span></span>  
  
|<span data-ttu-id="5c4ad-203">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-203">ColumnName</span></span>|<span data-ttu-id="5c4ad-204">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="5c4ad-206">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-206">String</span></span>|  
|<span data-ttu-id="5c4ad-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="5c4ad-208">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-208">String</span></span>|  
|<span data-ttu-id="5c4ad-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="5c4ad-210">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-210">String</span></span>|  
|<span data-ttu-id="5c4ad-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="5c4ad-212">Int16</span><span class="sxs-lookup"><span data-stu-id="5c4ad-212">Int16</span></span>|  
|<span data-ttu-id="5c4ad-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="5c4ad-214">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-214">String</span></span>|  
|<span data-ttu-id="5c4ad-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-215">DESCRIPTION</span></span>|<span data-ttu-id="5c4ad-216">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-216">String</span></span>|  
|<span data-ttu-id="5c4ad-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-217">DATE_CREATED</span></span>|<span data-ttu-id="5c4ad-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c4ad-218">DateTime</span></span>|  
|<span data-ttu-id="5c4ad-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-219">DATE_MODIFIED</span></span>|<span data-ttu-id="5c4ad-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c4ad-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="5c4ad-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="5c4ad-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="5c4ad-222">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-222">ColumnName</span></span>|<span data-ttu-id="5c4ad-223">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="5c4ad-225">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-225">String</span></span>|  
|<span data-ttu-id="5c4ad-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="5c4ad-227">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-227">String</span></span>|  
|<span data-ttu-id="5c4ad-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="5c4ad-229">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-229">String</span></span>|  
|<span data-ttu-id="5c4ad-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-230">PARAMETER_NAME</span></span>|<span data-ttu-id="5c4ad-231">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-231">String</span></span>|  
|<span data-ttu-id="5c4ad-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="5c4ad-233">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-233">Int32</span></span>|  
|<span data-ttu-id="5c4ad-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="5c4ad-235">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-235">Int32</span></span>|  
|<span data-ttu-id="5c4ad-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="5c4ad-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="5c4ad-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-237">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="5c4ad-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="5c4ad-239">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-239">String</span></span>|  
|<span data-ttu-id="5c4ad-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-240">IS_NULLABLE</span></span>|<span data-ttu-id="5c4ad-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-241">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-242">DATA_TYPE</span></span>|<span data-ttu-id="5c4ad-243">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-243">Int32</span></span>|  
|<span data-ttu-id="5c4ad-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5c4ad-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="5c4ad-245">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-245">Int64</span></span>|  
|<span data-ttu-id="5c4ad-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5c4ad-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="5c4ad-247">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-247">Int64</span></span>|  
|<span data-ttu-id="5c4ad-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="5c4ad-249">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-249">Int32</span></span>|  
|<span data-ttu-id="5c4ad-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="5c4ad-251">Int16</span><span class="sxs-lookup"><span data-stu-id="5c4ad-251">Int16</span></span>|  
|<span data-ttu-id="5c4ad-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-252">DESCRIPTION</span></span>|<span data-ttu-id="5c4ad-253">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-253">String</span></span>|  
|<span data-ttu-id="5c4ad-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-254">TYPE_NAME</span></span>|<span data-ttu-id="5c4ad-255">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-255">String</span></span>|  
|<span data-ttu-id="5c4ad-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="5c4ad-257">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="5c4ad-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="5c4ad-258">Catalog</span></span>  
  
|<span data-ttu-id="5c4ad-259">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-259">ColumnName</span></span>|<span data-ttu-id="5c4ad-260">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-261">CATALOG_NAME</span></span>|<span data-ttu-id="5c4ad-262">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-262">String</span></span>|  
|<span data-ttu-id="5c4ad-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-263">DESCRIPTION</span></span>|<span data-ttu-id="5c4ad-264">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="5c4ad-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="5c4ad-265">Indexes</span></span>  
  
|<span data-ttu-id="5c4ad-266">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-266">ColumnName</span></span>|<span data-ttu-id="5c4ad-267">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-268">TABLE_CATALOG</span></span>|<span data-ttu-id="5c4ad-269">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-269">String</span></span>|  
|<span data-ttu-id="5c4ad-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="5c4ad-271">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-271">String</span></span>|  
|<span data-ttu-id="5c4ad-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-272">TABLE_NAME</span></span>|<span data-ttu-id="5c4ad-273">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-273">String</span></span>|  
|<span data-ttu-id="5c4ad-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-274">INDEX_CATALOG</span></span>|<span data-ttu-id="5c4ad-275">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-275">String</span></span>|  
|<span data-ttu-id="5c4ad-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="5c4ad-277">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-277">String</span></span>|  
|<span data-ttu-id="5c4ad-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-278">INDEX_NAME</span></span>|<span data-ttu-id="5c4ad-279">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-279">String</span></span>|  
|<span data-ttu-id="5c4ad-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="5c4ad-280">PRIMARY_KEY</span></span>|<span data-ttu-id="5c4ad-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-281">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-282">UNIQUE</span></span>|<span data-ttu-id="5c4ad-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-283">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-284">CLUSTERED</span></span>|<span data-ttu-id="5c4ad-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-285">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-286">TYPE</span></span>|<span data-ttu-id="5c4ad-287">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-287">Int32</span></span>|  
|<span data-ttu-id="5c4ad-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="5c4ad-288">FILL_FACTOR</span></span>|<span data-ttu-id="5c4ad-289">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-289">Int32</span></span>|  
|<span data-ttu-id="5c4ad-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-290">INITIAL_SIZE</span></span>|<span data-ttu-id="5c4ad-291">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-291">Int32</span></span>|  
|<span data-ttu-id="5c4ad-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="5c4ad-292">NULLS</span></span>|<span data-ttu-id="5c4ad-293">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-293">Int32</span></span>|  
|<span data-ttu-id="5c4ad-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="5c4ad-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="5c4ad-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-295">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-296">AUTO_UPDATE</span></span>|<span data-ttu-id="5c4ad-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-297">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-298">NULL_COLLATION</span></span>|<span data-ttu-id="5c4ad-299">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-299">Int32</span></span>|  
|<span data-ttu-id="5c4ad-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="5c4ad-301">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-301">Int64</span></span>|  
|<span data-ttu-id="5c4ad-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-302">COLUMN_NAME</span></span>|<span data-ttu-id="5c4ad-303">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-303">String</span></span>|  
|<span data-ttu-id="5c4ad-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-304">COLUMN_GUID</span></span>|<span data-ttu-id="5c4ad-305">Guid</span><span class="sxs-lookup"><span data-stu-id="5c4ad-305">Guid</span></span>|  
|<span data-ttu-id="5c4ad-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-306">COLUMN_PROPID</span></span>|<span data-ttu-id="5c4ad-307">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-307">Int64</span></span>|  
|<span data-ttu-id="5c4ad-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-308">COLLATION</span></span>|<span data-ttu-id="5c4ad-309">Int16</span><span class="sxs-lookup"><span data-stu-id="5c4ad-309">Int16</span></span>|  
|<span data-ttu-id="5c4ad-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="5c4ad-310">CARDINALITY</span></span>|<span data-ttu-id="5c4ad-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="5c4ad-311">Decimal</span></span>|  
|<span data-ttu-id="5c4ad-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="5c4ad-312">PAGES</span></span>|<span data-ttu-id="5c4ad-313">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-313">Int32</span></span>|  
|<span data-ttu-id="5c4ad-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-314">FILTER_CONDITION</span></span>|<span data-ttu-id="5c4ad-315">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-315">String</span></span>|  
|<span data-ttu-id="5c4ad-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-316">INTEGRATED</span></span>|<span data-ttu-id="5c4ad-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="5c4ad-318">Provider OLE DB per Microsoft Oracle</span><span class="sxs-lookup"><span data-stu-id="5c4ad-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="5c4ad-319">Oltre alle raccolte di schemi comuni, il driver OLE DB per Microsoft Oracle supporta le seguenti raccolte di schemi specifici:</span><span class="sxs-lookup"><span data-stu-id="5c4ad-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="5c4ad-320">Tabelle</span><span class="sxs-lookup"><span data-stu-id="5c4ad-320">Tables</span></span>  
  
-   <span data-ttu-id="5c4ad-321">Colonne</span><span class="sxs-lookup"><span data-stu-id="5c4ad-321">Columns</span></span>  
  
-   <span data-ttu-id="5c4ad-322">Procedure</span><span class="sxs-lookup"><span data-stu-id="5c4ad-322">Procedures</span></span>  
  
-   <span data-ttu-id="5c4ad-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="5c4ad-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="5c4ad-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="5c4ad-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="5c4ad-325">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="5c4ad-325">Views</span></span>  
  
-   <span data-ttu-id="5c4ad-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="5c4ad-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="5c4ad-327">Tabelle</span><span class="sxs-lookup"><span data-stu-id="5c4ad-327">Tables</span></span>  
  
|<span data-ttu-id="5c4ad-328">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-328">ColumnName</span></span>|<span data-ttu-id="5c4ad-329">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-330">TABLE_CATALOG</span></span>|<span data-ttu-id="5c4ad-331">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-331">String</span></span>|  
|<span data-ttu-id="5c4ad-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="5c4ad-333">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-333">String</span></span>|  
|<span data-ttu-id="5c4ad-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-334">TABLE_NAME</span></span>|<span data-ttu-id="5c4ad-335">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-335">String</span></span>|  
|<span data-ttu-id="5c4ad-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-336">TABLE_TYPE</span></span>|<span data-ttu-id="5c4ad-337">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-337">String</span></span>|  
|<span data-ttu-id="5c4ad-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-338">TABLE_GUID</span></span>|<span data-ttu-id="5c4ad-339">Guid</span><span class="sxs-lookup"><span data-stu-id="5c4ad-339">Guid</span></span>|  
|<span data-ttu-id="5c4ad-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-340">DESCRIPTION</span></span>|<span data-ttu-id="5c4ad-341">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-341">String</span></span>|  
|<span data-ttu-id="5c4ad-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-342">TABLE_PROPID</span></span>|<span data-ttu-id="5c4ad-343">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-343">Int64</span></span>|  
|<span data-ttu-id="5c4ad-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-344">DATE_CREATED</span></span>|<span data-ttu-id="5c4ad-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c4ad-345">DateTime</span></span>|  
|<span data-ttu-id="5c4ad-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-346">DATE_MODIFIED</span></span>|<span data-ttu-id="5c4ad-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c4ad-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="5c4ad-348">Colonne</span><span class="sxs-lookup"><span data-stu-id="5c4ad-348">Columns</span></span>  
  
|<span data-ttu-id="5c4ad-349">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-349">ColumnName</span></span>|<span data-ttu-id="5c4ad-350">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-351">TABLE_CATALOG</span></span>|<span data-ttu-id="5c4ad-352">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-352">String</span></span>|  
|<span data-ttu-id="5c4ad-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="5c4ad-354">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-354">String</span></span>|  
|<span data-ttu-id="5c4ad-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-355">TABLE_NAME</span></span>|<span data-ttu-id="5c4ad-356">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-356">String</span></span>|  
|<span data-ttu-id="5c4ad-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-357">COLUMN_NAME</span></span>|<span data-ttu-id="5c4ad-358">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-358">String</span></span>|  
|<span data-ttu-id="5c4ad-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-359">COLUMN_GUID</span></span>|<span data-ttu-id="5c4ad-360">Guid</span><span class="sxs-lookup"><span data-stu-id="5c4ad-360">Guid</span></span>|  
|<span data-ttu-id="5c4ad-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-361">COLUMN_PROPID</span></span>|<span data-ttu-id="5c4ad-362">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-362">Int64</span></span>|  
|<span data-ttu-id="5c4ad-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="5c4ad-364">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-364">Int64</span></span>|  
|<span data-ttu-id="5c4ad-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="5c4ad-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="5c4ad-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-366">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="5c4ad-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="5c4ad-368">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-368">String</span></span>|  
|<span data-ttu-id="5c4ad-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="5c4ad-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="5c4ad-370">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-370">Int64</span></span>|  
|<span data-ttu-id="5c4ad-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-371">IS_NULLABLE</span></span>|<span data-ttu-id="5c4ad-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-372">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-373">DATA_TYPE</span></span>|<span data-ttu-id="5c4ad-374">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-374">Int32</span></span>|  
|<span data-ttu-id="5c4ad-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-375">TYPE_GUID</span></span>|<span data-ttu-id="5c4ad-376">Guid</span><span class="sxs-lookup"><span data-stu-id="5c4ad-376">Guid</span></span>|  
|<span data-ttu-id="5c4ad-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5c4ad-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="5c4ad-378">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-378">Int64</span></span>|  
|<span data-ttu-id="5c4ad-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5c4ad-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="5c4ad-380">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-380">Int64</span></span>|  
|<span data-ttu-id="5c4ad-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="5c4ad-382">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-382">Int32</span></span>|  
|<span data-ttu-id="5c4ad-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="5c4ad-384">Int16</span><span class="sxs-lookup"><span data-stu-id="5c4ad-384">Int16</span></span>|  
|<span data-ttu-id="5c4ad-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="5c4ad-386">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-386">Int64</span></span>|  
|<span data-ttu-id="5c4ad-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="5c4ad-388">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-388">String</span></span>|  
|<span data-ttu-id="5c4ad-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="5c4ad-390">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-390">String</span></span>|  
|<span data-ttu-id="5c4ad-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="5c4ad-392">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-392">String</span></span>|  
|<span data-ttu-id="5c4ad-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="5c4ad-394">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-394">String</span></span>|  
|<span data-ttu-id="5c4ad-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="5c4ad-396">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-396">String</span></span>|  
|<span data-ttu-id="5c4ad-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-397">COLLATION_NAME</span></span>|<span data-ttu-id="5c4ad-398">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-398">String</span></span>|  
|<span data-ttu-id="5c4ad-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="5c4ad-400">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-400">String</span></span>|  
|<span data-ttu-id="5c4ad-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="5c4ad-402">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-402">String</span></span>|  
|<span data-ttu-id="5c4ad-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-403">DOMAIN_NAME</span></span>|<span data-ttu-id="5c4ad-404">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-404">String</span></span>|  
|<span data-ttu-id="5c4ad-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-405">DESCRIPTION</span></span>|<span data-ttu-id="5c4ad-406">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="5c4ad-407">Procedure</span><span class="sxs-lookup"><span data-stu-id="5c4ad-407">Procedures</span></span>  
  
|<span data-ttu-id="5c4ad-408">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-408">ColumnName</span></span>|<span data-ttu-id="5c4ad-409">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="5c4ad-411">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-411">String</span></span>|  
|<span data-ttu-id="5c4ad-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="5c4ad-413">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-413">String</span></span>|  
|<span data-ttu-id="5c4ad-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="5c4ad-415">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-415">String</span></span>|  
|<span data-ttu-id="5c4ad-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="5c4ad-417">Int16</span><span class="sxs-lookup"><span data-stu-id="5c4ad-417">Int16</span></span>|  
|<span data-ttu-id="5c4ad-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="5c4ad-419">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-419">String</span></span>|  
|<span data-ttu-id="5c4ad-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-420">DESCRIPTION</span></span>|<span data-ttu-id="5c4ad-421">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-421">String</span></span>|  
|<span data-ttu-id="5c4ad-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-422">DATE_CREATED</span></span>|<span data-ttu-id="5c4ad-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c4ad-423">DateTime</span></span>|  
|<span data-ttu-id="5c4ad-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-424">DATE_MODIFIED</span></span>|<span data-ttu-id="5c4ad-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c4ad-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="5c4ad-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="5c4ad-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="5c4ad-427">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-427">ColumnName</span></span>|<span data-ttu-id="5c4ad-428">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="5c4ad-430">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-430">String</span></span>|  
|<span data-ttu-id="5c4ad-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="5c4ad-432">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-432">String</span></span>|  
|<span data-ttu-id="5c4ad-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="5c4ad-434">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-434">String</span></span>|  
|<span data-ttu-id="5c4ad-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-435">COLUMN_NAME</span></span>|<span data-ttu-id="5c4ad-436">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-436">String</span></span>|  
|<span data-ttu-id="5c4ad-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-437">COLUMN_GUID</span></span>|<span data-ttu-id="5c4ad-438">Guid</span><span class="sxs-lookup"><span data-stu-id="5c4ad-438">Guid</span></span>|  
|<span data-ttu-id="5c4ad-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-439">COLUMN_PROPID</span></span>|<span data-ttu-id="5c4ad-440">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-440">Int64</span></span>|  
|<span data-ttu-id="5c4ad-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="5c4ad-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="5c4ad-442">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-442">Int64</span></span>|  
|<span data-ttu-id="5c4ad-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="5c4ad-444">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-444">Int64</span></span>|  
|<span data-ttu-id="5c4ad-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-445">IS_NULLABLE</span></span>|<span data-ttu-id="5c4ad-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-446">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-447">DATA_TYPE</span></span>|<span data-ttu-id="5c4ad-448">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-448">Int32</span></span>|  
|<span data-ttu-id="5c4ad-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-449">TYPE_GUID</span></span>|<span data-ttu-id="5c4ad-450">Guid</span><span class="sxs-lookup"><span data-stu-id="5c4ad-450">Guid</span></span>|  
|<span data-ttu-id="5c4ad-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5c4ad-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="5c4ad-452">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-452">Int64</span></span>|  
|<span data-ttu-id="5c4ad-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5c4ad-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="5c4ad-454">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-454">Int64</span></span>|  
|<span data-ttu-id="5c4ad-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="5c4ad-456">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-456">Int32</span></span>|  
|<span data-ttu-id="5c4ad-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="5c4ad-458">Int16</span><span class="sxs-lookup"><span data-stu-id="5c4ad-458">Int16</span></span>|  
|<span data-ttu-id="5c4ad-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-459">DESCRIPTION</span></span>|<span data-ttu-id="5c4ad-460">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-460">String</span></span>|  
|<span data-ttu-id="5c4ad-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="5c4ad-461">OVERLOAD</span></span>|<span data-ttu-id="5c4ad-462">Int16</span><span class="sxs-lookup"><span data-stu-id="5c4ad-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="5c4ad-463">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="5c4ad-463">Views</span></span>  
  
|<span data-ttu-id="5c4ad-464">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-464">ColumnName</span></span>|<span data-ttu-id="5c4ad-465">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-466">TABLE_CATALOG</span></span>|<span data-ttu-id="5c4ad-467">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-467">String</span></span>|  
|<span data-ttu-id="5c4ad-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="5c4ad-469">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-469">String</span></span>|  
|<span data-ttu-id="5c4ad-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-470">TABLE_NAME</span></span>|<span data-ttu-id="5c4ad-471">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-471">String</span></span>|  
|<span data-ttu-id="5c4ad-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="5c4ad-473">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-473">String</span></span>|  
|<span data-ttu-id="5c4ad-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-474">CHECK_OPTION</span></span>|<span data-ttu-id="5c4ad-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-475">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-476">IS_UPDATABLE</span></span>|<span data-ttu-id="5c4ad-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-477">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-478">DESCRIPTION</span></span>|<span data-ttu-id="5c4ad-479">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-479">String</span></span>|  
|<span data-ttu-id="5c4ad-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-480">DATE_CREATED</span></span>|<span data-ttu-id="5c4ad-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c4ad-481">DateTime</span></span>|  
|<span data-ttu-id="5c4ad-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-482">DATE_MODIFIED</span></span>|<span data-ttu-id="5c4ad-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c4ad-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="5c4ad-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="5c4ad-484">Indexes</span></span>  
  
|<span data-ttu-id="5c4ad-485">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-485">ColumnName</span></span>|<span data-ttu-id="5c4ad-486">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-487">TABLE_CATALOG</span></span>|<span data-ttu-id="5c4ad-488">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-488">String</span></span>|  
|<span data-ttu-id="5c4ad-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="5c4ad-490">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-490">String</span></span>|  
|<span data-ttu-id="5c4ad-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-491">TABLE_NAME</span></span>|<span data-ttu-id="5c4ad-492">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-492">String</span></span>|  
|<span data-ttu-id="5c4ad-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-493">INDEX_CATALOG</span></span>|<span data-ttu-id="5c4ad-494">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-494">String</span></span>|  
|<span data-ttu-id="5c4ad-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="5c4ad-496">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-496">String</span></span>|  
|<span data-ttu-id="5c4ad-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-497">INDEX_NAME</span></span>|<span data-ttu-id="5c4ad-498">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-498">String</span></span>|  
|<span data-ttu-id="5c4ad-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="5c4ad-499">PRIMARY_KEY</span></span>|<span data-ttu-id="5c4ad-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-500">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-501">UNIQUE</span></span>|<span data-ttu-id="5c4ad-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-502">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-503">CLUSTERED</span></span>|<span data-ttu-id="5c4ad-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-504">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-505">TYPE</span></span>|<span data-ttu-id="5c4ad-506">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-506">Int32</span></span>|  
|<span data-ttu-id="5c4ad-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="5c4ad-507">FILL_FACTOR</span></span>|<span data-ttu-id="5c4ad-508">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-508">Int32</span></span>|  
|<span data-ttu-id="5c4ad-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-509">INITIAL_SIZE</span></span>|<span data-ttu-id="5c4ad-510">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-510">Int32</span></span>|  
|<span data-ttu-id="5c4ad-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="5c4ad-511">NULLS</span></span>|<span data-ttu-id="5c4ad-512">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-512">Int32</span></span>|  
|<span data-ttu-id="5c4ad-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="5c4ad-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="5c4ad-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-514">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-515">AUTO_UPDATE</span></span>|<span data-ttu-id="5c4ad-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-516">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-517">NULL_COLLATION</span></span>|<span data-ttu-id="5c4ad-518">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-518">Int32</span></span>|  
|<span data-ttu-id="5c4ad-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="5c4ad-520">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-520">Int64</span></span>|  
|<span data-ttu-id="5c4ad-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-521">COLUMN_NAME</span></span>|<span data-ttu-id="5c4ad-522">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-522">String</span></span>|  
|<span data-ttu-id="5c4ad-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-523">COLUMN_GUID</span></span>|<span data-ttu-id="5c4ad-524">Guid</span><span class="sxs-lookup"><span data-stu-id="5c4ad-524">Guid</span></span>|  
|<span data-ttu-id="5c4ad-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-525">COLUMN_PROPID</span></span>|<span data-ttu-id="5c4ad-526">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-526">Int64</span></span>|  
|<span data-ttu-id="5c4ad-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-527">COLLATION</span></span>|<span data-ttu-id="5c4ad-528">Int16</span><span class="sxs-lookup"><span data-stu-id="5c4ad-528">Int16</span></span>|  
|<span data-ttu-id="5c4ad-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="5c4ad-529">CARDINALITY</span></span>|<span data-ttu-id="5c4ad-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="5c4ad-530">Decimal</span></span>|  
|<span data-ttu-id="5c4ad-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="5c4ad-531">PAGES</span></span>|<span data-ttu-id="5c4ad-532">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-532">Int32</span></span>|  
|<span data-ttu-id="5c4ad-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-533">FILTER_CONDITION</span></span>|<span data-ttu-id="5c4ad-534">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-534">String</span></span>|  
|<span data-ttu-id="5c4ad-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-535">INTEGRATED</span></span>|<span data-ttu-id="5c4ad-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="5c4ad-537">Provider OLE DB per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="5c4ad-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="5c4ad-538">Oltre alle raccolte di schemi comuni, il driver OLE DB di Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c4ad-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="5c4ad-539">Tabelle</span><span class="sxs-lookup"><span data-stu-id="5c4ad-539">Tables</span></span>  
  
-   <span data-ttu-id="5c4ad-540">Colonne</span><span class="sxs-lookup"><span data-stu-id="5c4ad-540">Columns</span></span>  
  
-   <span data-ttu-id="5c4ad-541">Procedure</span><span class="sxs-lookup"><span data-stu-id="5c4ad-541">Procedures</span></span>  
  
-   <span data-ttu-id="5c4ad-542">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="5c4ad-542">Views</span></span>  
  
-   <span data-ttu-id="5c4ad-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="5c4ad-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="5c4ad-544">Tabelle</span><span class="sxs-lookup"><span data-stu-id="5c4ad-544">Tables</span></span>  
  
|<span data-ttu-id="5c4ad-545">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-545">ColumnName</span></span>|<span data-ttu-id="5c4ad-546">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-547">TABLE_CATALOG</span></span>|<span data-ttu-id="5c4ad-548">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-548">String</span></span>|  
|<span data-ttu-id="5c4ad-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="5c4ad-550">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-550">String</span></span>|  
|<span data-ttu-id="5c4ad-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-551">TABLE_NAME</span></span>|<span data-ttu-id="5c4ad-552">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-552">String</span></span>|  
|<span data-ttu-id="5c4ad-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-553">TABLE_TYPE</span></span>|<span data-ttu-id="5c4ad-554">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-554">String</span></span>|  
|<span data-ttu-id="5c4ad-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-555">TABLE_GUID</span></span>|<span data-ttu-id="5c4ad-556">Guid</span><span class="sxs-lookup"><span data-stu-id="5c4ad-556">Guid</span></span>|  
|<span data-ttu-id="5c4ad-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-557">DESCRIPTION</span></span>|<span data-ttu-id="5c4ad-558">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-558">String</span></span>|  
|<span data-ttu-id="5c4ad-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-559">TABLE_PROPID</span></span>|<span data-ttu-id="5c4ad-560">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-560">Int64</span></span>|  
|<span data-ttu-id="5c4ad-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-561">DATE_CREATED</span></span>|<span data-ttu-id="5c4ad-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c4ad-562">DateTime</span></span>|  
|<span data-ttu-id="5c4ad-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-563">DATE_MODIFIED</span></span>|<span data-ttu-id="5c4ad-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c4ad-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="5c4ad-565">Colonne</span><span class="sxs-lookup"><span data-stu-id="5c4ad-565">Columns</span></span>  
  
|<span data-ttu-id="5c4ad-566">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-566">ColumnName</span></span>|<span data-ttu-id="5c4ad-567">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-568">TABLE_CATALOG</span></span>|<span data-ttu-id="5c4ad-569">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-569">String</span></span>|  
|<span data-ttu-id="5c4ad-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="5c4ad-571">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-571">String</span></span>|  
|<span data-ttu-id="5c4ad-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-572">TABLE_NAME</span></span>|<span data-ttu-id="5c4ad-573">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-573">String</span></span>|  
|<span data-ttu-id="5c4ad-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-574">COLUMN_NAME</span></span>|<span data-ttu-id="5c4ad-575">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-575">String</span></span>|  
|<span data-ttu-id="5c4ad-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-576">COLUMN_GUID</span></span>|<span data-ttu-id="5c4ad-577">Guid</span><span class="sxs-lookup"><span data-stu-id="5c4ad-577">Guid</span></span>|  
|<span data-ttu-id="5c4ad-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-578">COLUMN_PROPID</span></span>|<span data-ttu-id="5c4ad-579">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-579">Int64</span></span>|  
|<span data-ttu-id="5c4ad-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="5c4ad-581">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-581">Int64</span></span>|  
|<span data-ttu-id="5c4ad-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="5c4ad-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="5c4ad-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-583">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="5c4ad-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="5c4ad-585">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-585">String</span></span>|  
|<span data-ttu-id="5c4ad-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="5c4ad-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="5c4ad-587">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-587">Int64</span></span>|  
|<span data-ttu-id="5c4ad-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-588">IS_NULLABLE</span></span>|<span data-ttu-id="5c4ad-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-589">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-590">DATA_TYPE</span></span>|<span data-ttu-id="5c4ad-591">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-591">Int32</span></span>|  
|<span data-ttu-id="5c4ad-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-592">TYPE_GUID</span></span>|<span data-ttu-id="5c4ad-593">Guid</span><span class="sxs-lookup"><span data-stu-id="5c4ad-593">Guid</span></span>|  
|<span data-ttu-id="5c4ad-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5c4ad-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="5c4ad-595">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-595">Int64</span></span>|  
|<span data-ttu-id="5c4ad-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5c4ad-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="5c4ad-597">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-597">Int64</span></span>|  
|<span data-ttu-id="5c4ad-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="5c4ad-599">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-599">Int32</span></span>|  
|<span data-ttu-id="5c4ad-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="5c4ad-601">Int16</span><span class="sxs-lookup"><span data-stu-id="5c4ad-601">Int16</span></span>|  
|<span data-ttu-id="5c4ad-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="5c4ad-603">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-603">Int64</span></span>|  
|<span data-ttu-id="5c4ad-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="5c4ad-605">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-605">String</span></span>|  
|<span data-ttu-id="5c4ad-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="5c4ad-607">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-607">String</span></span>|  
|<span data-ttu-id="5c4ad-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="5c4ad-609">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-609">String</span></span>|  
|<span data-ttu-id="5c4ad-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="5c4ad-611">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-611">String</span></span>|  
|<span data-ttu-id="5c4ad-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="5c4ad-613">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-613">String</span></span>|  
|<span data-ttu-id="5c4ad-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-614">COLLATION_NAME</span></span>|<span data-ttu-id="5c4ad-615">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-615">String</span></span>|  
|<span data-ttu-id="5c4ad-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="5c4ad-617">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-617">String</span></span>|  
|<span data-ttu-id="5c4ad-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="5c4ad-619">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-619">String</span></span>|  
|<span data-ttu-id="5c4ad-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-620">DOMAIN_NAME</span></span>|<span data-ttu-id="5c4ad-621">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-621">String</span></span>|  
|<span data-ttu-id="5c4ad-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-622">DESCRIPTION</span></span>|<span data-ttu-id="5c4ad-623">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="5c4ad-624">Procedure</span><span class="sxs-lookup"><span data-stu-id="5c4ad-624">Procedures</span></span>  
  
|<span data-ttu-id="5c4ad-625">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-625">ColumnName</span></span>|<span data-ttu-id="5c4ad-626">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="5c4ad-628">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-628">String</span></span>|  
|<span data-ttu-id="5c4ad-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="5c4ad-630">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-630">String</span></span>|  
|<span data-ttu-id="5c4ad-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="5c4ad-632">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-632">String</span></span>|  
|<span data-ttu-id="5c4ad-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="5c4ad-634">Int16</span><span class="sxs-lookup"><span data-stu-id="5c4ad-634">Int16</span></span>|  
|<span data-ttu-id="5c4ad-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="5c4ad-636">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-636">String</span></span>|  
|<span data-ttu-id="5c4ad-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-637">DESCRIPTION</span></span>|<span data-ttu-id="5c4ad-638">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-638">String</span></span>|  
|<span data-ttu-id="5c4ad-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-639">DATE_CREATED</span></span>|<span data-ttu-id="5c4ad-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c4ad-640">DateTime</span></span>|  
|<span data-ttu-id="5c4ad-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-641">DATE_MODIFIED</span></span>|<span data-ttu-id="5c4ad-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c4ad-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="5c4ad-643">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="5c4ad-643">Views</span></span>  
  
|<span data-ttu-id="5c4ad-644">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-644">ColumnName</span></span>|<span data-ttu-id="5c4ad-645">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-646">TABLE_CATALOG</span></span>|<span data-ttu-id="5c4ad-647">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-647">String</span></span>|  
|<span data-ttu-id="5c4ad-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="5c4ad-649">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-649">String</span></span>|  
|<span data-ttu-id="5c4ad-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-650">TABLE_NAME</span></span>|<span data-ttu-id="5c4ad-651">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-651">String</span></span>|  
|<span data-ttu-id="5c4ad-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="5c4ad-653">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-653">String</span></span>|  
|<span data-ttu-id="5c4ad-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-654">CHECK_OPTION</span></span>|<span data-ttu-id="5c4ad-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-655">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-656">IS_UPDATABLE</span></span>|<span data-ttu-id="5c4ad-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-657">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-658">DESCRIPTION</span></span>|<span data-ttu-id="5c4ad-659">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-659">String</span></span>|  
|<span data-ttu-id="5c4ad-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-660">DATE_CREATED</span></span>|<span data-ttu-id="5c4ad-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c4ad-661">DateTime</span></span>|  
|<span data-ttu-id="5c4ad-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-662">DATE_MODIFIED</span></span>|<span data-ttu-id="5c4ad-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="5c4ad-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="5c4ad-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="5c4ad-664">Indexes</span></span>  
  
|<span data-ttu-id="5c4ad-665">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5c4ad-665">ColumnName</span></span>|<span data-ttu-id="5c4ad-666">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="5c4ad-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-667">TABLE_CATALOG</span></span>|<span data-ttu-id="5c4ad-668">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-668">String</span></span>|  
|<span data-ttu-id="5c4ad-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="5c4ad-670">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-670">String</span></span>|  
|<span data-ttu-id="5c4ad-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-671">TABLE_NAME</span></span>|<span data-ttu-id="5c4ad-672">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-672">String</span></span>|  
|<span data-ttu-id="5c4ad-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="5c4ad-673">INDEX_CATALOG</span></span>|<span data-ttu-id="5c4ad-674">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-674">String</span></span>|  
|<span data-ttu-id="5c4ad-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="5c4ad-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="5c4ad-676">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-676">String</span></span>|  
|<span data-ttu-id="5c4ad-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-677">INDEX_NAME</span></span>|<span data-ttu-id="5c4ad-678">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-678">String</span></span>|  
|<span data-ttu-id="5c4ad-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="5c4ad-679">PRIMARY_KEY</span></span>|<span data-ttu-id="5c4ad-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-680">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-681">UNIQUE</span></span>|<span data-ttu-id="5c4ad-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-682">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-683">CLUSTERED</span></span>|<span data-ttu-id="5c4ad-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-684">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-685">TYPE</span></span>|<span data-ttu-id="5c4ad-686">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-686">Int32</span></span>|  
|<span data-ttu-id="5c4ad-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="5c4ad-687">FILL_FACTOR</span></span>|<span data-ttu-id="5c4ad-688">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-688">Int32</span></span>|  
|<span data-ttu-id="5c4ad-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-689">INITIAL_SIZE</span></span>|<span data-ttu-id="5c4ad-690">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-690">Int32</span></span>|  
|<span data-ttu-id="5c4ad-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="5c4ad-691">NULLS</span></span>|<span data-ttu-id="5c4ad-692">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-692">Int32</span></span>|  
|<span data-ttu-id="5c4ad-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="5c4ad-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="5c4ad-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-694">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="5c4ad-695">AUTO_UPDATE</span></span>|<span data-ttu-id="5c4ad-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c4ad-696">Boolean</span></span>|  
|<span data-ttu-id="5c4ad-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-697">NULL_COLLATION</span></span>|<span data-ttu-id="5c4ad-698">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-698">Int32</span></span>|  
|<span data-ttu-id="5c4ad-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="5c4ad-700">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-700">Int64</span></span>|  
|<span data-ttu-id="5c4ad-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="5c4ad-701">COLUMN_NAME</span></span>|<span data-ttu-id="5c4ad-702">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-702">String</span></span>|  
|<span data-ttu-id="5c4ad-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-703">COLUMN_GUID</span></span>|<span data-ttu-id="5c4ad-704">Guid</span><span class="sxs-lookup"><span data-stu-id="5c4ad-704">Guid</span></span>|  
|<span data-ttu-id="5c4ad-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="5c4ad-705">COLUMN_PROPID</span></span>|<span data-ttu-id="5c4ad-706">Int64</span><span class="sxs-lookup"><span data-stu-id="5c4ad-706">Int64</span></span>|  
|<span data-ttu-id="5c4ad-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-707">COLLATION</span></span>|<span data-ttu-id="5c4ad-708">Int16</span><span class="sxs-lookup"><span data-stu-id="5c4ad-708">Int16</span></span>|  
|<span data-ttu-id="5c4ad-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="5c4ad-709">CARDINALITY</span></span>|<span data-ttu-id="5c4ad-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="5c4ad-710">Decimal</span></span>|  
|<span data-ttu-id="5c4ad-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="5c4ad-711">PAGES</span></span>|<span data-ttu-id="5c4ad-712">Int32</span><span class="sxs-lookup"><span data-stu-id="5c4ad-712">Int32</span></span>|  
|<span data-ttu-id="5c4ad-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="5c4ad-713">FILTER_CONDITION</span></span>|<span data-ttu-id="5c4ad-714">String</span><span class="sxs-lookup"><span data-stu-id="5c4ad-714">String</span></span>|  
|<span data-ttu-id="5c4ad-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="5c4ad-715">INTEGRATED</span></span>|<span data-ttu-id="5c4ad-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="5c4ad-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c4ad-717">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c4ad-717">See Also</span></span>  
 [<span data-ttu-id="5c4ad-718">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="5c4ad-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
