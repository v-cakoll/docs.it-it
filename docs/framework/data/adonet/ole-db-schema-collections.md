---
title: Raccolte di schemi OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771995"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="92e1b-102">Raccolte di schemi OLE DB</span><span class="sxs-lookup"><span data-stu-id="92e1b-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="92e1b-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per i provider OLE DB per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="92e1b-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="92e1b-104">Provider OLE DB per Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="92e1b-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="92e1b-105">Il Driver OLE DB Microsoft SQL Server supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="92e1b-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="92e1b-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="92e1b-106">Tables</span></span>  
  
- <span data-ttu-id="92e1b-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="92e1b-107">Columns</span></span>  
  
- <span data-ttu-id="92e1b-108">Procedure</span><span class="sxs-lookup"><span data-stu-id="92e1b-108">Procedures</span></span>  
  
- <span data-ttu-id="92e1b-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="92e1b-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="92e1b-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="92e1b-110">Catalog</span></span>  
  
- <span data-ttu-id="92e1b-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="92e1b-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="92e1b-112">Tabelle</span><span class="sxs-lookup"><span data-stu-id="92e1b-112">Tables</span></span>  
  
|<span data-ttu-id="92e1b-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-113">ColumnName</span></span>|<span data-ttu-id="92e1b-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-115">TABLE_CATALOG</span></span>|<span data-ttu-id="92e1b-116">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-116">String</span></span>|  
|<span data-ttu-id="92e1b-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="92e1b-118">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-118">String</span></span>|  
|<span data-ttu-id="92e1b-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-119">TABLE_NAME</span></span>|<span data-ttu-id="92e1b-120">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-120">String</span></span>|  
|<span data-ttu-id="92e1b-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="92e1b-121">TABLE_TYPE</span></span>|<span data-ttu-id="92e1b-122">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-122">String</span></span>|  
|<span data-ttu-id="92e1b-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-123">TABLE_GUID</span></span>|<span data-ttu-id="92e1b-124">GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-124">Guid</span></span>|  
|<span data-ttu-id="92e1b-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="92e1b-125">DESCRIPTION</span></span>|<span data-ttu-id="92e1b-126">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-126">String</span></span>|  
|<span data-ttu-id="92e1b-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="92e1b-127">TABLE_PROPID</span></span>|<span data-ttu-id="92e1b-128">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-128">Int64</span></span>|  
|<span data-ttu-id="92e1b-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="92e1b-129">DATE_CREATED</span></span>|<span data-ttu-id="92e1b-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="92e1b-130">DateTime</span></span>|  
|<span data-ttu-id="92e1b-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="92e1b-131">DATE_MODIFIED</span></span>|<span data-ttu-id="92e1b-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="92e1b-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="92e1b-133">Colonne</span><span class="sxs-lookup"><span data-stu-id="92e1b-133">Columns</span></span>  
  
|<span data-ttu-id="92e1b-134">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-134">ColumnName</span></span>|<span data-ttu-id="92e1b-135">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-136">TABLE_CATALOG</span></span>|<span data-ttu-id="92e1b-137">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-137">String</span></span>|  
|<span data-ttu-id="92e1b-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="92e1b-139">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-139">String</span></span>|  
|<span data-ttu-id="92e1b-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-140">TABLE_NAME</span></span>|<span data-ttu-id="92e1b-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-141">String</span></span>|  
|<span data-ttu-id="92e1b-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-142">COLUMN_NAME</span></span>|<span data-ttu-id="92e1b-143">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-143">String</span></span>|  
|<span data-ttu-id="92e1b-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-144">COLUMN_GUID</span></span>|<span data-ttu-id="92e1b-145">GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-145">Guid</span></span>|  
|<span data-ttu-id="92e1b-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="92e1b-146">COLUMN_PROPID</span></span>|<span data-ttu-id="92e1b-147">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-147">Int64</span></span>|  
|<span data-ttu-id="92e1b-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="92e1b-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="92e1b-149">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-149">Int64</span></span>|  
|<span data-ttu-id="92e1b-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="92e1b-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="92e1b-151">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-151">Boolean</span></span>|  
|<span data-ttu-id="92e1b-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="92e1b-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="92e1b-153">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-153">String</span></span>|  
|<span data-ttu-id="92e1b-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="92e1b-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="92e1b-155">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-155">Int64</span></span>|  
|<span data-ttu-id="92e1b-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="92e1b-156">IS_NULLABLE</span></span>|<span data-ttu-id="92e1b-157">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-157">Boolean</span></span>|  
|<span data-ttu-id="92e1b-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="92e1b-158">DATA_TYPE</span></span>|<span data-ttu-id="92e1b-159">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-159">Int32</span></span>|  
|<span data-ttu-id="92e1b-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-160">TYPE_GUID</span></span>|<span data-ttu-id="92e1b-161">GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-161">Guid</span></span>|  
|<span data-ttu-id="92e1b-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="92e1b-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="92e1b-163">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-163">Int64</span></span>|  
|<span data-ttu-id="92e1b-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="92e1b-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="92e1b-165">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-165">Int64</span></span>|  
|<span data-ttu-id="92e1b-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="92e1b-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="92e1b-167">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-167">Int32</span></span>|  
|<span data-ttu-id="92e1b-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="92e1b-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="92e1b-169">Int16</span><span class="sxs-lookup"><span data-stu-id="92e1b-169">Int16</span></span>|  
|<span data-ttu-id="92e1b-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="92e1b-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="92e1b-171">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-171">Int64</span></span>|  
|<span data-ttu-id="92e1b-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="92e1b-173">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-173">String</span></span>|  
|<span data-ttu-id="92e1b-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="92e1b-175">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-175">String</span></span>|  
|<span data-ttu-id="92e1b-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="92e1b-177">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-177">String</span></span>|  
|<span data-ttu-id="92e1b-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="92e1b-179">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-179">String</span></span>|  
|<span data-ttu-id="92e1b-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="92e1b-181">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-181">String</span></span>|  
|<span data-ttu-id="92e1b-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-182">COLLATION_NAME</span></span>|<span data-ttu-id="92e1b-183">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-183">String</span></span>|  
|<span data-ttu-id="92e1b-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="92e1b-185">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-185">String</span></span>|  
|<span data-ttu-id="92e1b-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="92e1b-187">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-187">String</span></span>|  
|<span data-ttu-id="92e1b-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-188">DOMAIN_NAME</span></span>|<span data-ttu-id="92e1b-189">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-189">String</span></span>|  
|<span data-ttu-id="92e1b-190">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="92e1b-190">DESCRIPTION</span></span>|<span data-ttu-id="92e1b-191">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-191">String</span></span>|  
|<span data-ttu-id="92e1b-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="92e1b-192">COLUMN_LCID</span></span>|<span data-ttu-id="92e1b-193">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-193">Int32</span></span>|  
|<span data-ttu-id="92e1b-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="92e1b-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="92e1b-195">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-195">Int32</span></span>|  
|<span data-ttu-id="92e1b-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="92e1b-196">COLUMN_SORTID</span></span>|<span data-ttu-id="92e1b-197">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-197">Int32</span></span>|  
|<span data-ttu-id="92e1b-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="92e1b-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="92e1b-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="92e1b-199">Byte[]</span></span>|  
|<span data-ttu-id="92e1b-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="92e1b-200">IS_COMPUTED</span></span>|<span data-ttu-id="92e1b-201">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="92e1b-202">Procedure</span><span class="sxs-lookup"><span data-stu-id="92e1b-202">Procedures</span></span>  
  
|<span data-ttu-id="92e1b-203">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-203">ColumnName</span></span>|<span data-ttu-id="92e1b-204">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="92e1b-206">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-206">String</span></span>|  
|<span data-ttu-id="92e1b-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="92e1b-208">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-208">String</span></span>|  
|<span data-ttu-id="92e1b-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="92e1b-210">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-210">String</span></span>|  
|<span data-ttu-id="92e1b-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="92e1b-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="92e1b-212">Int16</span><span class="sxs-lookup"><span data-stu-id="92e1b-212">Int16</span></span>|  
|<span data-ttu-id="92e1b-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="92e1b-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="92e1b-214">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-214">String</span></span>|  
|<span data-ttu-id="92e1b-215">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="92e1b-215">DESCRIPTION</span></span>|<span data-ttu-id="92e1b-216">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-216">String</span></span>|  
|<span data-ttu-id="92e1b-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="92e1b-217">DATE_CREATED</span></span>|<span data-ttu-id="92e1b-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="92e1b-218">DateTime</span></span>|  
|<span data-ttu-id="92e1b-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="92e1b-219">DATE_MODIFIED</span></span>|<span data-ttu-id="92e1b-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="92e1b-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="92e1b-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="92e1b-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="92e1b-222">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-222">ColumnName</span></span>|<span data-ttu-id="92e1b-223">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="92e1b-225">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-225">String</span></span>|  
|<span data-ttu-id="92e1b-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="92e1b-227">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-227">String</span></span>|  
|<span data-ttu-id="92e1b-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="92e1b-229">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-229">String</span></span>|  
|<span data-ttu-id="92e1b-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-230">PARAMETER_NAME</span></span>|<span data-ttu-id="92e1b-231">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-231">String</span></span>|  
|<span data-ttu-id="92e1b-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="92e1b-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="92e1b-233">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-233">Int32</span></span>|  
|<span data-ttu-id="92e1b-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="92e1b-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="92e1b-235">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-235">Int32</span></span>|  
|<span data-ttu-id="92e1b-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="92e1b-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="92e1b-237">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-237">Boolean</span></span>|  
|<span data-ttu-id="92e1b-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="92e1b-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="92e1b-239">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-239">String</span></span>|  
|<span data-ttu-id="92e1b-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="92e1b-240">IS_NULLABLE</span></span>|<span data-ttu-id="92e1b-241">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-241">Boolean</span></span>|  
|<span data-ttu-id="92e1b-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="92e1b-242">DATA_TYPE</span></span>|<span data-ttu-id="92e1b-243">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-243">Int32</span></span>|  
|<span data-ttu-id="92e1b-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="92e1b-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="92e1b-245">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-245">Int64</span></span>|  
|<span data-ttu-id="92e1b-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="92e1b-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="92e1b-247">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-247">Int64</span></span>|  
|<span data-ttu-id="92e1b-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="92e1b-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="92e1b-249">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-249">Int32</span></span>|  
|<span data-ttu-id="92e1b-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="92e1b-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="92e1b-251">Int16</span><span class="sxs-lookup"><span data-stu-id="92e1b-251">Int16</span></span>|  
|<span data-ttu-id="92e1b-252">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="92e1b-252">DESCRIPTION</span></span>|<span data-ttu-id="92e1b-253">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-253">String</span></span>|  
|<span data-ttu-id="92e1b-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-254">TYPE_NAME</span></span>|<span data-ttu-id="92e1b-255">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-255">String</span></span>|  
|<span data-ttu-id="92e1b-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="92e1b-257">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="92e1b-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="92e1b-258">Catalog</span></span>  
  
|<span data-ttu-id="92e1b-259">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-259">ColumnName</span></span>|<span data-ttu-id="92e1b-260">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-261">CATALOG_NAME</span></span>|<span data-ttu-id="92e1b-262">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-262">String</span></span>|  
|<span data-ttu-id="92e1b-263">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="92e1b-263">DESCRIPTION</span></span>|<span data-ttu-id="92e1b-264">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="92e1b-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="92e1b-265">Indexes</span></span>  
  
|<span data-ttu-id="92e1b-266">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-266">ColumnName</span></span>|<span data-ttu-id="92e1b-267">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-268">TABLE_CATALOG</span></span>|<span data-ttu-id="92e1b-269">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-269">String</span></span>|  
|<span data-ttu-id="92e1b-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="92e1b-271">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-271">String</span></span>|  
|<span data-ttu-id="92e1b-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-272">TABLE_NAME</span></span>|<span data-ttu-id="92e1b-273">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-273">String</span></span>|  
|<span data-ttu-id="92e1b-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-274">INDEX_CATALOG</span></span>|<span data-ttu-id="92e1b-275">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-275">String</span></span>|  
|<span data-ttu-id="92e1b-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="92e1b-277">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-277">String</span></span>|  
|<span data-ttu-id="92e1b-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-278">INDEX_NAME</span></span>|<span data-ttu-id="92e1b-279">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-279">String</span></span>|  
|<span data-ttu-id="92e1b-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="92e1b-280">PRIMARY_KEY</span></span>|<span data-ttu-id="92e1b-281">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-281">Boolean</span></span>|  
|<span data-ttu-id="92e1b-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="92e1b-282">UNIQUE</span></span>|<span data-ttu-id="92e1b-283">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-283">Boolean</span></span>|  
|<span data-ttu-id="92e1b-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="92e1b-284">CLUSTERED</span></span>|<span data-ttu-id="92e1b-285">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-285">Boolean</span></span>|  
|<span data-ttu-id="92e1b-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="92e1b-286">TYPE</span></span>|<span data-ttu-id="92e1b-287">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-287">Int32</span></span>|  
|<span data-ttu-id="92e1b-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="92e1b-288">FILL_FACTOR</span></span>|<span data-ttu-id="92e1b-289">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-289">Int32</span></span>|  
|<span data-ttu-id="92e1b-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="92e1b-290">INITIAL_SIZE</span></span>|<span data-ttu-id="92e1b-291">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-291">Int32</span></span>|  
|<span data-ttu-id="92e1b-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="92e1b-292">NULLS</span></span>|<span data-ttu-id="92e1b-293">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-293">Int32</span></span>|  
|<span data-ttu-id="92e1b-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="92e1b-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="92e1b-295">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-295">Boolean</span></span>|  
|<span data-ttu-id="92e1b-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="92e1b-296">AUTO_UPDATE</span></span>|<span data-ttu-id="92e1b-297">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-297">Boolean</span></span>|  
|<span data-ttu-id="92e1b-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="92e1b-298">NULL_COLLATION</span></span>|<span data-ttu-id="92e1b-299">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-299">Int32</span></span>|  
|<span data-ttu-id="92e1b-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="92e1b-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="92e1b-301">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-301">Int64</span></span>|  
|<span data-ttu-id="92e1b-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-302">COLUMN_NAME</span></span>|<span data-ttu-id="92e1b-303">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-303">String</span></span>|  
|<span data-ttu-id="92e1b-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-304">COLUMN_GUID</span></span>|<span data-ttu-id="92e1b-305">GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-305">Guid</span></span>|  
|<span data-ttu-id="92e1b-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="92e1b-306">COLUMN_PROPID</span></span>|<span data-ttu-id="92e1b-307">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-307">Int64</span></span>|  
|<span data-ttu-id="92e1b-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="92e1b-308">COLLATION</span></span>|<span data-ttu-id="92e1b-309">Int16</span><span class="sxs-lookup"><span data-stu-id="92e1b-309">Int16</span></span>|  
|<span data-ttu-id="92e1b-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="92e1b-310">CARDINALITY</span></span>|<span data-ttu-id="92e1b-311">Decimale</span><span class="sxs-lookup"><span data-stu-id="92e1b-311">Decimal</span></span>|  
|<span data-ttu-id="92e1b-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="92e1b-312">PAGES</span></span>|<span data-ttu-id="92e1b-313">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-313">Int32</span></span>|  
|<span data-ttu-id="92e1b-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="92e1b-314">FILTER_CONDITION</span></span>|<span data-ttu-id="92e1b-315">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-315">String</span></span>|  
|<span data-ttu-id="92e1b-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="92e1b-316">INTEGRATED</span></span>|<span data-ttu-id="92e1b-317">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="92e1b-318">Provider OLE DB per Microsoft Oracle</span><span class="sxs-lookup"><span data-stu-id="92e1b-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="92e1b-319">Oltre alle raccolte di schemi comuni, il driver OLE DB per Microsoft Oracle supporta le seguenti raccolte di schemi specifici:</span><span class="sxs-lookup"><span data-stu-id="92e1b-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="92e1b-320">Tabelle</span><span class="sxs-lookup"><span data-stu-id="92e1b-320">Tables</span></span>  
  
- <span data-ttu-id="92e1b-321">Colonne</span><span class="sxs-lookup"><span data-stu-id="92e1b-321">Columns</span></span>  
  
- <span data-ttu-id="92e1b-322">Procedure</span><span class="sxs-lookup"><span data-stu-id="92e1b-322">Procedures</span></span>  
  
- <span data-ttu-id="92e1b-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="92e1b-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="92e1b-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="92e1b-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="92e1b-325">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="92e1b-325">Views</span></span>  
  
- <span data-ttu-id="92e1b-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="92e1b-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="92e1b-327">Tabelle</span><span class="sxs-lookup"><span data-stu-id="92e1b-327">Tables</span></span>  
  
|<span data-ttu-id="92e1b-328">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-328">ColumnName</span></span>|<span data-ttu-id="92e1b-329">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-330">TABLE_CATALOG</span></span>|<span data-ttu-id="92e1b-331">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-331">String</span></span>|  
|<span data-ttu-id="92e1b-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="92e1b-333">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-333">String</span></span>|  
|<span data-ttu-id="92e1b-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-334">TABLE_NAME</span></span>|<span data-ttu-id="92e1b-335">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-335">String</span></span>|  
|<span data-ttu-id="92e1b-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="92e1b-336">TABLE_TYPE</span></span>|<span data-ttu-id="92e1b-337">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-337">String</span></span>|  
|<span data-ttu-id="92e1b-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-338">TABLE_GUID</span></span>|<span data-ttu-id="92e1b-339">GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-339">Guid</span></span>|  
|<span data-ttu-id="92e1b-340">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="92e1b-340">DESCRIPTION</span></span>|<span data-ttu-id="92e1b-341">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-341">String</span></span>|  
|<span data-ttu-id="92e1b-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="92e1b-342">TABLE_PROPID</span></span>|<span data-ttu-id="92e1b-343">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-343">Int64</span></span>|  
|<span data-ttu-id="92e1b-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="92e1b-344">DATE_CREATED</span></span>|<span data-ttu-id="92e1b-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="92e1b-345">DateTime</span></span>|  
|<span data-ttu-id="92e1b-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="92e1b-346">DATE_MODIFIED</span></span>|<span data-ttu-id="92e1b-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="92e1b-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="92e1b-348">Colonne</span><span class="sxs-lookup"><span data-stu-id="92e1b-348">Columns</span></span>  
  
|<span data-ttu-id="92e1b-349">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-349">ColumnName</span></span>|<span data-ttu-id="92e1b-350">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-351">TABLE_CATALOG</span></span>|<span data-ttu-id="92e1b-352">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-352">String</span></span>|  
|<span data-ttu-id="92e1b-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="92e1b-354">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-354">String</span></span>|  
|<span data-ttu-id="92e1b-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-355">TABLE_NAME</span></span>|<span data-ttu-id="92e1b-356">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-356">String</span></span>|  
|<span data-ttu-id="92e1b-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-357">COLUMN_NAME</span></span>|<span data-ttu-id="92e1b-358">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-358">String</span></span>|  
|<span data-ttu-id="92e1b-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-359">COLUMN_GUID</span></span>|<span data-ttu-id="92e1b-360">GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-360">Guid</span></span>|  
|<span data-ttu-id="92e1b-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="92e1b-361">COLUMN_PROPID</span></span>|<span data-ttu-id="92e1b-362">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-362">Int64</span></span>|  
|<span data-ttu-id="92e1b-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="92e1b-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="92e1b-364">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-364">Int64</span></span>|  
|<span data-ttu-id="92e1b-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="92e1b-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="92e1b-366">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-366">Boolean</span></span>|  
|<span data-ttu-id="92e1b-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="92e1b-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="92e1b-368">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-368">String</span></span>|  
|<span data-ttu-id="92e1b-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="92e1b-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="92e1b-370">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-370">Int64</span></span>|  
|<span data-ttu-id="92e1b-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="92e1b-371">IS_NULLABLE</span></span>|<span data-ttu-id="92e1b-372">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-372">Boolean</span></span>|  
|<span data-ttu-id="92e1b-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="92e1b-373">DATA_TYPE</span></span>|<span data-ttu-id="92e1b-374">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-374">Int32</span></span>|  
|<span data-ttu-id="92e1b-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-375">TYPE_GUID</span></span>|<span data-ttu-id="92e1b-376">GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-376">Guid</span></span>|  
|<span data-ttu-id="92e1b-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="92e1b-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="92e1b-378">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-378">Int64</span></span>|  
|<span data-ttu-id="92e1b-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="92e1b-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="92e1b-380">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-380">Int64</span></span>|  
|<span data-ttu-id="92e1b-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="92e1b-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="92e1b-382">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-382">Int32</span></span>|  
|<span data-ttu-id="92e1b-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="92e1b-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="92e1b-384">Int16</span><span class="sxs-lookup"><span data-stu-id="92e1b-384">Int16</span></span>|  
|<span data-ttu-id="92e1b-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="92e1b-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="92e1b-386">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-386">Int64</span></span>|  
|<span data-ttu-id="92e1b-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="92e1b-388">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-388">String</span></span>|  
|<span data-ttu-id="92e1b-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="92e1b-390">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-390">String</span></span>|  
|<span data-ttu-id="92e1b-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="92e1b-392">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-392">String</span></span>|  
|<span data-ttu-id="92e1b-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="92e1b-394">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-394">String</span></span>|  
|<span data-ttu-id="92e1b-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="92e1b-396">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-396">String</span></span>|  
|<span data-ttu-id="92e1b-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-397">COLLATION_NAME</span></span>|<span data-ttu-id="92e1b-398">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-398">String</span></span>|  
|<span data-ttu-id="92e1b-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="92e1b-400">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-400">String</span></span>|  
|<span data-ttu-id="92e1b-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="92e1b-402">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-402">String</span></span>|  
|<span data-ttu-id="92e1b-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-403">DOMAIN_NAME</span></span>|<span data-ttu-id="92e1b-404">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-404">String</span></span>|  
|<span data-ttu-id="92e1b-405">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="92e1b-405">DESCRIPTION</span></span>|<span data-ttu-id="92e1b-406">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="92e1b-407">Procedure</span><span class="sxs-lookup"><span data-stu-id="92e1b-407">Procedures</span></span>  
  
|<span data-ttu-id="92e1b-408">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-408">ColumnName</span></span>|<span data-ttu-id="92e1b-409">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="92e1b-411">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-411">String</span></span>|  
|<span data-ttu-id="92e1b-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="92e1b-413">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-413">String</span></span>|  
|<span data-ttu-id="92e1b-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="92e1b-415">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-415">String</span></span>|  
|<span data-ttu-id="92e1b-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="92e1b-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="92e1b-417">Int16</span><span class="sxs-lookup"><span data-stu-id="92e1b-417">Int16</span></span>|  
|<span data-ttu-id="92e1b-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="92e1b-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="92e1b-419">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-419">String</span></span>|  
|<span data-ttu-id="92e1b-420">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="92e1b-420">DESCRIPTION</span></span>|<span data-ttu-id="92e1b-421">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-421">String</span></span>|  
|<span data-ttu-id="92e1b-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="92e1b-422">DATE_CREATED</span></span>|<span data-ttu-id="92e1b-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="92e1b-423">DateTime</span></span>|  
|<span data-ttu-id="92e1b-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="92e1b-424">DATE_MODIFIED</span></span>|<span data-ttu-id="92e1b-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="92e1b-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="92e1b-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="92e1b-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="92e1b-427">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-427">ColumnName</span></span>|<span data-ttu-id="92e1b-428">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="92e1b-430">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-430">String</span></span>|  
|<span data-ttu-id="92e1b-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="92e1b-432">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-432">String</span></span>|  
|<span data-ttu-id="92e1b-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="92e1b-434">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-434">String</span></span>|  
|<span data-ttu-id="92e1b-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-435">COLUMN_NAME</span></span>|<span data-ttu-id="92e1b-436">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-436">String</span></span>|  
|<span data-ttu-id="92e1b-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-437">COLUMN_GUID</span></span>|<span data-ttu-id="92e1b-438">GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-438">Guid</span></span>|  
|<span data-ttu-id="92e1b-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="92e1b-439">COLUMN_PROPID</span></span>|<span data-ttu-id="92e1b-440">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-440">Int64</span></span>|  
|<span data-ttu-id="92e1b-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="92e1b-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="92e1b-442">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-442">Int64</span></span>|  
|<span data-ttu-id="92e1b-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="92e1b-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="92e1b-444">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-444">Int64</span></span>|  
|<span data-ttu-id="92e1b-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="92e1b-445">IS_NULLABLE</span></span>|<span data-ttu-id="92e1b-446">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-446">Boolean</span></span>|  
|<span data-ttu-id="92e1b-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="92e1b-447">DATA_TYPE</span></span>|<span data-ttu-id="92e1b-448">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-448">Int32</span></span>|  
|<span data-ttu-id="92e1b-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-449">TYPE_GUID</span></span>|<span data-ttu-id="92e1b-450">GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-450">Guid</span></span>|  
|<span data-ttu-id="92e1b-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="92e1b-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="92e1b-452">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-452">Int64</span></span>|  
|<span data-ttu-id="92e1b-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="92e1b-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="92e1b-454">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-454">Int64</span></span>|  
|<span data-ttu-id="92e1b-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="92e1b-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="92e1b-456">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-456">Int32</span></span>|  
|<span data-ttu-id="92e1b-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="92e1b-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="92e1b-458">Int16</span><span class="sxs-lookup"><span data-stu-id="92e1b-458">Int16</span></span>|  
|<span data-ttu-id="92e1b-459">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="92e1b-459">DESCRIPTION</span></span>|<span data-ttu-id="92e1b-460">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-460">String</span></span>|  
|<span data-ttu-id="92e1b-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="92e1b-461">OVERLOAD</span></span>|<span data-ttu-id="92e1b-462">Int16</span><span class="sxs-lookup"><span data-stu-id="92e1b-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="92e1b-463">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="92e1b-463">Views</span></span>  
  
|<span data-ttu-id="92e1b-464">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-464">ColumnName</span></span>|<span data-ttu-id="92e1b-465">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-466">TABLE_CATALOG</span></span>|<span data-ttu-id="92e1b-467">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-467">String</span></span>|  
|<span data-ttu-id="92e1b-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="92e1b-469">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-469">String</span></span>|  
|<span data-ttu-id="92e1b-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-470">TABLE_NAME</span></span>|<span data-ttu-id="92e1b-471">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-471">String</span></span>|  
|<span data-ttu-id="92e1b-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="92e1b-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="92e1b-473">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-473">String</span></span>|  
|<span data-ttu-id="92e1b-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="92e1b-474">CHECK_OPTION</span></span>|<span data-ttu-id="92e1b-475">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-475">Boolean</span></span>|  
|<span data-ttu-id="92e1b-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="92e1b-476">IS_UPDATABLE</span></span>|<span data-ttu-id="92e1b-477">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-477">Boolean</span></span>|  
|<span data-ttu-id="92e1b-478">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="92e1b-478">DESCRIPTION</span></span>|<span data-ttu-id="92e1b-479">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-479">String</span></span>|  
|<span data-ttu-id="92e1b-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="92e1b-480">DATE_CREATED</span></span>|<span data-ttu-id="92e1b-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="92e1b-481">DateTime</span></span>|  
|<span data-ttu-id="92e1b-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="92e1b-482">DATE_MODIFIED</span></span>|<span data-ttu-id="92e1b-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="92e1b-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="92e1b-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="92e1b-484">Indexes</span></span>  
  
|<span data-ttu-id="92e1b-485">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-485">ColumnName</span></span>|<span data-ttu-id="92e1b-486">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-487">TABLE_CATALOG</span></span>|<span data-ttu-id="92e1b-488">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-488">String</span></span>|  
|<span data-ttu-id="92e1b-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="92e1b-490">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-490">String</span></span>|  
|<span data-ttu-id="92e1b-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-491">TABLE_NAME</span></span>|<span data-ttu-id="92e1b-492">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-492">String</span></span>|  
|<span data-ttu-id="92e1b-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-493">INDEX_CATALOG</span></span>|<span data-ttu-id="92e1b-494">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-494">String</span></span>|  
|<span data-ttu-id="92e1b-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="92e1b-496">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-496">String</span></span>|  
|<span data-ttu-id="92e1b-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-497">INDEX_NAME</span></span>|<span data-ttu-id="92e1b-498">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-498">String</span></span>|  
|<span data-ttu-id="92e1b-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="92e1b-499">PRIMARY_KEY</span></span>|<span data-ttu-id="92e1b-500">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-500">Boolean</span></span>|  
|<span data-ttu-id="92e1b-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="92e1b-501">UNIQUE</span></span>|<span data-ttu-id="92e1b-502">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-502">Boolean</span></span>|  
|<span data-ttu-id="92e1b-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="92e1b-503">CLUSTERED</span></span>|<span data-ttu-id="92e1b-504">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-504">Boolean</span></span>|  
|<span data-ttu-id="92e1b-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="92e1b-505">TYPE</span></span>|<span data-ttu-id="92e1b-506">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-506">Int32</span></span>|  
|<span data-ttu-id="92e1b-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="92e1b-507">FILL_FACTOR</span></span>|<span data-ttu-id="92e1b-508">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-508">Int32</span></span>|  
|<span data-ttu-id="92e1b-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="92e1b-509">INITIAL_SIZE</span></span>|<span data-ttu-id="92e1b-510">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-510">Int32</span></span>|  
|<span data-ttu-id="92e1b-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="92e1b-511">NULLS</span></span>|<span data-ttu-id="92e1b-512">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-512">Int32</span></span>|  
|<span data-ttu-id="92e1b-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="92e1b-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="92e1b-514">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-514">Boolean</span></span>|  
|<span data-ttu-id="92e1b-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="92e1b-515">AUTO_UPDATE</span></span>|<span data-ttu-id="92e1b-516">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-516">Boolean</span></span>|  
|<span data-ttu-id="92e1b-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="92e1b-517">NULL_COLLATION</span></span>|<span data-ttu-id="92e1b-518">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-518">Int32</span></span>|  
|<span data-ttu-id="92e1b-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="92e1b-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="92e1b-520">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-520">Int64</span></span>|  
|<span data-ttu-id="92e1b-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-521">COLUMN_NAME</span></span>|<span data-ttu-id="92e1b-522">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-522">String</span></span>|  
|<span data-ttu-id="92e1b-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-523">COLUMN_GUID</span></span>|<span data-ttu-id="92e1b-524">GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-524">Guid</span></span>|  
|<span data-ttu-id="92e1b-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="92e1b-525">COLUMN_PROPID</span></span>|<span data-ttu-id="92e1b-526">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-526">Int64</span></span>|  
|<span data-ttu-id="92e1b-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="92e1b-527">COLLATION</span></span>|<span data-ttu-id="92e1b-528">Int16</span><span class="sxs-lookup"><span data-stu-id="92e1b-528">Int16</span></span>|  
|<span data-ttu-id="92e1b-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="92e1b-529">CARDINALITY</span></span>|<span data-ttu-id="92e1b-530">Decimale</span><span class="sxs-lookup"><span data-stu-id="92e1b-530">Decimal</span></span>|  
|<span data-ttu-id="92e1b-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="92e1b-531">PAGES</span></span>|<span data-ttu-id="92e1b-532">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-532">Int32</span></span>|  
|<span data-ttu-id="92e1b-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="92e1b-533">FILTER_CONDITION</span></span>|<span data-ttu-id="92e1b-534">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-534">String</span></span>|  
|<span data-ttu-id="92e1b-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="92e1b-535">INTEGRATED</span></span>|<span data-ttu-id="92e1b-536">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="92e1b-537">Provider OLE DB per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="92e1b-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="92e1b-538">Oltre alle raccolte di schemi comuni, il driver OLE DB di Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="92e1b-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="92e1b-539">Tabelle</span><span class="sxs-lookup"><span data-stu-id="92e1b-539">Tables</span></span>  
  
- <span data-ttu-id="92e1b-540">Colonne</span><span class="sxs-lookup"><span data-stu-id="92e1b-540">Columns</span></span>  
  
- <span data-ttu-id="92e1b-541">Procedure</span><span class="sxs-lookup"><span data-stu-id="92e1b-541">Procedures</span></span>  
  
- <span data-ttu-id="92e1b-542">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="92e1b-542">Views</span></span>  
  
- <span data-ttu-id="92e1b-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="92e1b-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="92e1b-544">Tabelle</span><span class="sxs-lookup"><span data-stu-id="92e1b-544">Tables</span></span>  
  
|<span data-ttu-id="92e1b-545">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-545">ColumnName</span></span>|<span data-ttu-id="92e1b-546">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-547">TABLE_CATALOG</span></span>|<span data-ttu-id="92e1b-548">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-548">String</span></span>|  
|<span data-ttu-id="92e1b-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="92e1b-550">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-550">String</span></span>|  
|<span data-ttu-id="92e1b-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-551">TABLE_NAME</span></span>|<span data-ttu-id="92e1b-552">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-552">String</span></span>|  
|<span data-ttu-id="92e1b-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="92e1b-553">TABLE_TYPE</span></span>|<span data-ttu-id="92e1b-554">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-554">String</span></span>|  
|<span data-ttu-id="92e1b-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-555">TABLE_GUID</span></span>|<span data-ttu-id="92e1b-556">GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-556">Guid</span></span>|  
|<span data-ttu-id="92e1b-557">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="92e1b-557">DESCRIPTION</span></span>|<span data-ttu-id="92e1b-558">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-558">String</span></span>|  
|<span data-ttu-id="92e1b-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="92e1b-559">TABLE_PROPID</span></span>|<span data-ttu-id="92e1b-560">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-560">Int64</span></span>|  
|<span data-ttu-id="92e1b-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="92e1b-561">DATE_CREATED</span></span>|<span data-ttu-id="92e1b-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="92e1b-562">DateTime</span></span>|  
|<span data-ttu-id="92e1b-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="92e1b-563">DATE_MODIFIED</span></span>|<span data-ttu-id="92e1b-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="92e1b-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="92e1b-565">Colonne</span><span class="sxs-lookup"><span data-stu-id="92e1b-565">Columns</span></span>  
  
|<span data-ttu-id="92e1b-566">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-566">ColumnName</span></span>|<span data-ttu-id="92e1b-567">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-568">TABLE_CATALOG</span></span>|<span data-ttu-id="92e1b-569">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-569">String</span></span>|  
|<span data-ttu-id="92e1b-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="92e1b-571">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-571">String</span></span>|  
|<span data-ttu-id="92e1b-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-572">TABLE_NAME</span></span>|<span data-ttu-id="92e1b-573">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-573">String</span></span>|  
|<span data-ttu-id="92e1b-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-574">COLUMN_NAME</span></span>|<span data-ttu-id="92e1b-575">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-575">String</span></span>|  
|<span data-ttu-id="92e1b-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-576">COLUMN_GUID</span></span>|<span data-ttu-id="92e1b-577">GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-577">Guid</span></span>|  
|<span data-ttu-id="92e1b-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="92e1b-578">COLUMN_PROPID</span></span>|<span data-ttu-id="92e1b-579">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-579">Int64</span></span>|  
|<span data-ttu-id="92e1b-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="92e1b-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="92e1b-581">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-581">Int64</span></span>|  
|<span data-ttu-id="92e1b-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="92e1b-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="92e1b-583">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-583">Boolean</span></span>|  
|<span data-ttu-id="92e1b-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="92e1b-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="92e1b-585">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-585">String</span></span>|  
|<span data-ttu-id="92e1b-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="92e1b-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="92e1b-587">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-587">Int64</span></span>|  
|<span data-ttu-id="92e1b-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="92e1b-588">IS_NULLABLE</span></span>|<span data-ttu-id="92e1b-589">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-589">Boolean</span></span>|  
|<span data-ttu-id="92e1b-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="92e1b-590">DATA_TYPE</span></span>|<span data-ttu-id="92e1b-591">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-591">Int32</span></span>|  
|<span data-ttu-id="92e1b-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-592">TYPE_GUID</span></span>|<span data-ttu-id="92e1b-593">GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-593">Guid</span></span>|  
|<span data-ttu-id="92e1b-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="92e1b-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="92e1b-595">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-595">Int64</span></span>|  
|<span data-ttu-id="92e1b-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="92e1b-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="92e1b-597">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-597">Int64</span></span>|  
|<span data-ttu-id="92e1b-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="92e1b-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="92e1b-599">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-599">Int32</span></span>|  
|<span data-ttu-id="92e1b-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="92e1b-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="92e1b-601">Int16</span><span class="sxs-lookup"><span data-stu-id="92e1b-601">Int16</span></span>|  
|<span data-ttu-id="92e1b-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="92e1b-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="92e1b-603">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-603">Int64</span></span>|  
|<span data-ttu-id="92e1b-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="92e1b-605">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-605">String</span></span>|  
|<span data-ttu-id="92e1b-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="92e1b-607">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-607">String</span></span>|  
|<span data-ttu-id="92e1b-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="92e1b-609">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-609">String</span></span>|  
|<span data-ttu-id="92e1b-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="92e1b-611">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-611">String</span></span>|  
|<span data-ttu-id="92e1b-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="92e1b-613">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-613">String</span></span>|  
|<span data-ttu-id="92e1b-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-614">COLLATION_NAME</span></span>|<span data-ttu-id="92e1b-615">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-615">String</span></span>|  
|<span data-ttu-id="92e1b-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="92e1b-617">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-617">String</span></span>|  
|<span data-ttu-id="92e1b-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="92e1b-619">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-619">String</span></span>|  
|<span data-ttu-id="92e1b-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-620">DOMAIN_NAME</span></span>|<span data-ttu-id="92e1b-621">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-621">String</span></span>|  
|<span data-ttu-id="92e1b-622">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="92e1b-622">DESCRIPTION</span></span>|<span data-ttu-id="92e1b-623">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="92e1b-624">Procedure</span><span class="sxs-lookup"><span data-stu-id="92e1b-624">Procedures</span></span>  
  
|<span data-ttu-id="92e1b-625">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-625">ColumnName</span></span>|<span data-ttu-id="92e1b-626">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="92e1b-628">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-628">String</span></span>|  
|<span data-ttu-id="92e1b-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="92e1b-630">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-630">String</span></span>|  
|<span data-ttu-id="92e1b-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="92e1b-632">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-632">String</span></span>|  
|<span data-ttu-id="92e1b-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="92e1b-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="92e1b-634">Int16</span><span class="sxs-lookup"><span data-stu-id="92e1b-634">Int16</span></span>|  
|<span data-ttu-id="92e1b-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="92e1b-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="92e1b-636">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-636">String</span></span>|  
|<span data-ttu-id="92e1b-637">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="92e1b-637">DESCRIPTION</span></span>|<span data-ttu-id="92e1b-638">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-638">String</span></span>|  
|<span data-ttu-id="92e1b-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="92e1b-639">DATE_CREATED</span></span>|<span data-ttu-id="92e1b-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="92e1b-640">DateTime</span></span>|  
|<span data-ttu-id="92e1b-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="92e1b-641">DATE_MODIFIED</span></span>|<span data-ttu-id="92e1b-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="92e1b-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="92e1b-643">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="92e1b-643">Views</span></span>  
  
|<span data-ttu-id="92e1b-644">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-644">ColumnName</span></span>|<span data-ttu-id="92e1b-645">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-646">TABLE_CATALOG</span></span>|<span data-ttu-id="92e1b-647">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-647">String</span></span>|  
|<span data-ttu-id="92e1b-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="92e1b-649">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-649">String</span></span>|  
|<span data-ttu-id="92e1b-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-650">TABLE_NAME</span></span>|<span data-ttu-id="92e1b-651">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-651">String</span></span>|  
|<span data-ttu-id="92e1b-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="92e1b-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="92e1b-653">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-653">String</span></span>|  
|<span data-ttu-id="92e1b-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="92e1b-654">CHECK_OPTION</span></span>|<span data-ttu-id="92e1b-655">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-655">Boolean</span></span>|  
|<span data-ttu-id="92e1b-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="92e1b-656">IS_UPDATABLE</span></span>|<span data-ttu-id="92e1b-657">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-657">Boolean</span></span>|  
|<span data-ttu-id="92e1b-658">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="92e1b-658">DESCRIPTION</span></span>|<span data-ttu-id="92e1b-659">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-659">String</span></span>|  
|<span data-ttu-id="92e1b-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="92e1b-660">DATE_CREATED</span></span>|<span data-ttu-id="92e1b-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="92e1b-661">DateTime</span></span>|  
|<span data-ttu-id="92e1b-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="92e1b-662">DATE_MODIFIED</span></span>|<span data-ttu-id="92e1b-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="92e1b-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="92e1b-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="92e1b-664">Indexes</span></span>  
  
|<span data-ttu-id="92e1b-665">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="92e1b-665">ColumnName</span></span>|<span data-ttu-id="92e1b-666">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="92e1b-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-667">TABLE_CATALOG</span></span>|<span data-ttu-id="92e1b-668">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-668">String</span></span>|  
|<span data-ttu-id="92e1b-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="92e1b-670">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-670">String</span></span>|  
|<span data-ttu-id="92e1b-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-671">TABLE_NAME</span></span>|<span data-ttu-id="92e1b-672">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-672">String</span></span>|  
|<span data-ttu-id="92e1b-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="92e1b-673">INDEX_CATALOG</span></span>|<span data-ttu-id="92e1b-674">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-674">String</span></span>|  
|<span data-ttu-id="92e1b-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="92e1b-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="92e1b-676">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-676">String</span></span>|  
|<span data-ttu-id="92e1b-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-677">INDEX_NAME</span></span>|<span data-ttu-id="92e1b-678">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-678">String</span></span>|  
|<span data-ttu-id="92e1b-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="92e1b-679">PRIMARY_KEY</span></span>|<span data-ttu-id="92e1b-680">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-680">Boolean</span></span>|  
|<span data-ttu-id="92e1b-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="92e1b-681">UNIQUE</span></span>|<span data-ttu-id="92e1b-682">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-682">Boolean</span></span>|  
|<span data-ttu-id="92e1b-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="92e1b-683">CLUSTERED</span></span>|<span data-ttu-id="92e1b-684">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-684">Boolean</span></span>|  
|<span data-ttu-id="92e1b-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="92e1b-685">TYPE</span></span>|<span data-ttu-id="92e1b-686">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-686">Int32</span></span>|  
|<span data-ttu-id="92e1b-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="92e1b-687">FILL_FACTOR</span></span>|<span data-ttu-id="92e1b-688">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-688">Int32</span></span>|  
|<span data-ttu-id="92e1b-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="92e1b-689">INITIAL_SIZE</span></span>|<span data-ttu-id="92e1b-690">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-690">Int32</span></span>|  
|<span data-ttu-id="92e1b-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="92e1b-691">NULLS</span></span>|<span data-ttu-id="92e1b-692">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-692">Int32</span></span>|  
|<span data-ttu-id="92e1b-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="92e1b-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="92e1b-694">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-694">Boolean</span></span>|  
|<span data-ttu-id="92e1b-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="92e1b-695">AUTO_UPDATE</span></span>|<span data-ttu-id="92e1b-696">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-696">Boolean</span></span>|  
|<span data-ttu-id="92e1b-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="92e1b-697">NULL_COLLATION</span></span>|<span data-ttu-id="92e1b-698">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-698">Int32</span></span>|  
|<span data-ttu-id="92e1b-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="92e1b-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="92e1b-700">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-700">Int64</span></span>|  
|<span data-ttu-id="92e1b-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="92e1b-701">COLUMN_NAME</span></span>|<span data-ttu-id="92e1b-702">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-702">String</span></span>|  
|<span data-ttu-id="92e1b-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-703">COLUMN_GUID</span></span>|<span data-ttu-id="92e1b-704">GUID</span><span class="sxs-lookup"><span data-stu-id="92e1b-704">Guid</span></span>|  
|<span data-ttu-id="92e1b-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="92e1b-705">COLUMN_PROPID</span></span>|<span data-ttu-id="92e1b-706">Int64</span><span class="sxs-lookup"><span data-stu-id="92e1b-706">Int64</span></span>|  
|<span data-ttu-id="92e1b-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="92e1b-707">COLLATION</span></span>|<span data-ttu-id="92e1b-708">Int16</span><span class="sxs-lookup"><span data-stu-id="92e1b-708">Int16</span></span>|  
|<span data-ttu-id="92e1b-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="92e1b-709">CARDINALITY</span></span>|<span data-ttu-id="92e1b-710">Decimale</span><span class="sxs-lookup"><span data-stu-id="92e1b-710">Decimal</span></span>|  
|<span data-ttu-id="92e1b-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="92e1b-711">PAGES</span></span>|<span data-ttu-id="92e1b-712">Int32</span><span class="sxs-lookup"><span data-stu-id="92e1b-712">Int32</span></span>|  
|<span data-ttu-id="92e1b-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="92e1b-713">FILTER_CONDITION</span></span>|<span data-ttu-id="92e1b-714">Stringa</span><span class="sxs-lookup"><span data-stu-id="92e1b-714">String</span></span>|  
|<span data-ttu-id="92e1b-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="92e1b-715">INTEGRATED</span></span>|<span data-ttu-id="92e1b-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="92e1b-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92e1b-717">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92e1b-717">See also</span></span>

- [<span data-ttu-id="92e1b-718">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="92e1b-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
