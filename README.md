# Payout-Fee-Kwai
SQL Statement
select hpa.reference_id, count(hp.uid), sum(hp.debit_fee)
from pay.hive_payout hp
join pay.hive_payer_account hpa on hpa.id = hp.payer_id
where hpa.reference_type = 'merchant'
and hpa.reference_id = 5051
and hp.paid_date between '2021-08-01 00:00:00' and '2021-08-31 23:59:59'
and hp.status = 'PA'
group by 1
