static void DWDV3699_Test(Args _args)
{
    CustDueReportDetailTmp CustDueReportDetailTmp;
    OME_CustReportDetailContract  OME_CustReportDetailContract= new OME_CustReportDetailContract();
    OME_CustReportDetailDP OME_CustReportDetailDP = new OME_CustReportDetailDP();
    OME_CustReportDetailContract.parmPerDate(mkDate(11,06,2013));
    OME_CustReportDetailContract.parmDateTo(mkDate(17,06,2013));
    OME_CustReportDetailDP.parmDataContract(OME_CustReportDetailContract);
    OME_CustReportDetailContract.parmnrOfInvoices(0);
    OME_CustReportDetailContract.parmTotalBalance(0);
    OME_CustReportDetailDP.processReport();
    CustDueReportDetailTmp = OME_CustReportDetailDP.getCustDueReportDetailTmp();
    while(CustDueReportDetailTmp.RecId)
    {
        info(CustDueReportDetailTmp.OME_Name);
        next CustDueReportDetailTmp ;
    }
}
