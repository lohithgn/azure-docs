[!INCLUDE [P2S FAQ All](vpn-gateway-faq-p2s-all-include.md)]

### Is RADIUS authentication supported on all Azure VPN Gateway SKUs?

RADIUS authentication is supported for VpnGw1, VpnGw2, and VpnGw3 SKUs. If you are using legacy SKUs, RADIUS authentication is supported on Standard and High Performance SKUs. It is not supported on the Basic Gateway SKU. 
 
### Is RADIUS authentication supported for the classic deployment model?
 
No. RADIUS authentication is not supported for the classic deployment model.
 
### Are 3rd-party RADIUS servers supported?

Yes, 3rd-party RADIUS servers are supported.
 
### What are the connectivity requirements to ensure that the Azure gateway is able to reach an on-premises RADIUS server?

A VPN Site-to-Site connection to the on-premises site, with the proper routes configured, is required.  
 
### Can traffic to an on-premises RADIUS server (from the Azure VPN gateway) be routed over an ExpressRoute connection?

No. It can only be routed over a Site-to-Site connection.
 
### Is there a change in the number of SSTP connections supported with RADIUS authentication? What is the maximum number of SSTP and IKEv2 connections supported?

There is no change in the maximum number of SSTP connections supported on a gateway with RADIUS authentication. It remains 128. The maximum number of connections supported is 128, irrespective of whether the gateway is configured for SSTP, IKEv2, or both.
 
### What is the difference between doing certificate authentication using a RADIUS server vs. using Azure native certificate authentication (by uploading a trusted certificate to Azure).

In RADIUS certificate authentication, the authentication request is forwarded to a RADIUS server that handles the actual certificate validation. This option is useful if you want to integrate with a certificate authentication infrastructure that you already have through RADIUS.
  
When using Azure for certificate authentication, the Azure VPN gateway performs the validation of the certificate. You need to upload your certificate public key to the gateway. You can also specify list of revoked certificates that shouldn’t be allowed to connect.  