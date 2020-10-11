<html>
<body>


<div ng-app='myApp' ng-controller='myCtrl'>
	<div class="row center"> 
		<div class="col s12 m12 l12"> 
			<div class="card">
				<div class="card-content">
					<span class="card-title">IP Subnet Calculator</span>
					<div class="divider"></div><br/>
					<input ng-model="oct0" type="number" min="0" max="255" style="width:50px"/>.
 					<input ng-model="oct1" type="number" min="0" max="255" style="width:50px"/>.
 					<input ng-model="oct2" type="number" min="0" max="255" style="width:50px"/>.
 					<input ng-model="oct3" type="number" min="0" max="255" style="width:50px"/>/
 					<input ng-model="prefix" type="number" min="0" max="32" style="width:50px"/>
					
					<br/>
					Class: {{class()}}<br/> 
 					Network Address: {{networkAddress()}}<br/> 
 					Subnet Mask: {{subnetMask()}}<br/> 
 					IP Binary: {{IPBinary()}}<br/> 
 					Network Binary: {{networkBinary}}<br/>
					Subnet Binary: {{subnetBinary()}}<br/> 
 					Network Bits: {{prefix}}<br/> 
 					Host Bits: {{32-prefix}}<br/> 
 					Subnet Bits: {{subnetBits()}}<br/>
					Total Subnets: {{totalSubnets()}}<br/>
 					Hosts Per Subnet: {{hostsPerSubnet()}}<br/> 
 					Total Hosts on Network: {{hostCount}}<br/> 
 					Hosts lost to Subnets: {{hostsLostToSubnets()}} 
 				</div> 
 			</div> 
 		</div> 
	</div>
</div>
</body>
</html>

<script>

//returns true if it is, else false
if(typeof Number.isInteger === "undefined") Number.prototype.isInteger = function(x) { return x % 1 === 0;};
//inserts a string into another string at the specified index
String.prototype.insert = function(index, string) {
  if(index > 0)
    return this.toString().substring(0, index) + string + this.toString().substring(index, this.toString().length);
  else
    return string + this.toString();
};
//repeats a string 'x' times
if(typeof String.repeat === "undefined") {
	String.prototype.repeat = function(x) {
		var temp = "";
		for(var i=0;i<x;i++) temp += this.toString();
		return temp;
	};

</script>
