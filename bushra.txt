package com.armorcode.authserver.risk.impl;
import com.armorcode.base.common.dto.SubProductEsFilterDto;
import com.armorcode.base.enums.EnvironmentEnumType;
public class RiskEsServiceImpl {
    public void getPageRequestForSubProductEsFilter(SubProductEsFilterDto dto) {
        // getEnvironmentName() returns null → calling .equals() on it throws NullPointerException
        if (dto.getEnvironmentName().equals(EnvironmentEnumType.PROD)) {
            System.out.println("Environment is PROD.");
        } else {
            System.out.println("Environment is not PROD.");
        }
    }
    public static void main(String[] args) {
        RiskEsServiceImpl service = new RiskEsServiceImpl();
        SubProductEsFilterDto dto = new SubProductEsFilterDto();
        service.getPageRequestForSubProductEsFilter(dto);  // Triggers the NPE
    }
}
